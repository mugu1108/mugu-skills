---
name: layout-fix
description: スライドのレイアウト問題を自動検出・修正します。Playwrightでスクリーンショットを撮影し、オーバーフローや表示崩れを検出して修正提案を行います。
category: quality
triggers:
  - "スライドのレイアウトを確認"
  - "スライドのはみ出しチェック"
  - "layout fix"
  - "slide layout check"
tools:
  - Read
  - Write
  - Edit
  - Bash
---

# /layout-fix - スライドレイアウト自動検出・修正

**説明**: Marpスライドのレイアウト問題（オーバーフロー、はみ出し）を自動検出し、修正を行います。

## 使用方法

```
スライドのレイアウトを確認して: slides/my-presentation.md
```

## 概要

Marp CLIでHTMLを生成し、Playwright MCPでスクリーンショット撮影とオーバーフロー検出を行います。問題のあるスライドは自動的に修正し、再検証まで行います。

## 起動タイミング

- スライド生成後のレイアウト検証
- 既存スライドの表示崩れ修正
- コードブロックやリストが多いスライドのはみ出しチェック

## 前提条件

- Marp CLI (`@marp-team/marp-cli`)
- Playwright MCP サーバー接続済み

## ワークフローステップ

### ステップ1: HTML生成

対象のMarpスライドファイルからHTMLを生成する。

```bash
npx @marp-team/marp-cli <slide.md> --html -o .tmp-preview/<name>.html
```

### ステップ2: スクリーンショット撮影

Playwright MCPの `browser_navigate` でHTMLを開き、`browser_run_code` で各スライドを撮影する。ビューポートは 1280x720 (16:9)。

```javascript
// browser_run_code で実行
async (page) => {
  await page.setViewportSize({ width: 1280, height: 720 })
  const slides = await page.locator('section').all()
  for (let i = 0; i < slides.length; i++) {
    await slides[i].screenshot({ path: `.tmp-preview/slide-${i + 1}.png` })
  }
  return `${slides.length} slides captured`
}
```

### ステップ3: オーバーフロー検出

各スライドの `section` 要素で `scrollHeight > clientHeight` をチェックする。

```javascript
// browser_evaluate で実行
() => {
  const sections = document.querySelectorAll('section')
  return Array.from(sections).map((s, i) => ({
    slide: i + 1,
    overflow: s.scrollHeight > s.clientHeight,
    scrollHeight: s.scrollHeight,
    clientHeight: s.clientHeight,
  })).filter(r => r.overflow)
}
```

### ステップ4: 自動修正

オーバーフローが検出されたスライドに対して以下を適用する。

| 条件 | 修正方法 |
|------|---------|
| コードブロックが9行以上 | 複数スライドに分割 |
| リスト項目が7個以上 | 複数スライドに分割 |
| テキスト量過多 | 要約または分割 |

修正後、ステップ1-3を再実行して検証する。オーバーフローが解消されるまで繰り返す（最大3回）。

## 使用例

### 例1: コードブロックのはみ出し修正

```
入力: 15行のコードブロックを含むスライド
検出: slide 5 - overflow: true (scrollHeight: 820, clientHeight: 720)
修正:
  - スライド5を5(1/2)と5(2/2)に分割
  - コードブロックを7行 + 8行に分割
再検証: overflow なし
```

## 注意事項

- `.tmp-preview/` ディレクトリは一時ファイル用。`.gitignore` に追加推奨
- Playwright MCPが接続されていない場合はスクリーンショット撮影をスキップし、静的解析のみ行う
- 修正ループは最大3回まで。解消しない場合は手動確認を促す
