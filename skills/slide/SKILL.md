---
name: slide
description: Marp形式のプレゼンテーションスライドを自動生成します。インラインHTML+カードベースデザイン+SVG図解で、視覚的に分かりやすいスライドを作成します。
category: documentation
triggers:
  - "スライドを作成"
  - "プレゼンテーション資料を作成"
  - "セミナー資料を作成"
  - "ワークショップ資料を作成"
  - "Marpスライド生成"
  - "製品紹介スライド"
  - "create slide"
  - "create presentation"
tools:
  - Read
  - Write
  - Grep
  - Glob
---

# Slideスキル

Marp形式のプレゼンテーションスライドを自動生成する。

**品質基準**: `slides/vibe-coding-intro-20260402.md` をリファレンス実装として参照すること。

## テンプレート

| テンプレート | 用途 | キーワード |
|-------------|------|-----------|
| `templates/general-presentation.md` | 登壇・セミナー | セミナー, カンファレンス, 勉強会 |
| `templates/hands-on-workshop.md` | ハンズオン | ハンズオン, 実習, ワークショップ |
| `templates/product-intro.md` | 製品紹介 | 製品, サービス, ツール紹介 |

## ワークフロー

### 1. 要件収集

以下を確認（AskUserQuestionツール使用）:
- テンプレートタイプ
- 対象者（初心者/中級者/上級者）
- 時間（例: 30分、1時間）
- トピック
- 学習目標（ワークショップの場合）

### 2. リファレンス読み込み（最重要ステップ）

**このステップが生成品質の8割を決める。絶対にスキップしない。**

スライド生成前に `slides/vibe-coding-intro-20260402.md` を **全行** Readツールで読み込む。
このファイルは448行のMarpスライド実装で、以下をすべて含む:
- フロントマターの正確な書き方
- インラインHTML + CSS styleによるカードレイアウトの実例
- 2カラムgrid、会話UI、ナンバード要点、カテゴリラベルなどのパターン
- SVG図解の埋め込み方法
- Teal Trustカラーの実際の使われ方（ミント背景、ティールボーダー、ピンク課題カード）
- 1スライド1メッセージの情報密度の実例

**読み込み手順**:
1. `slides/vibe-coding-intro-20260402.md` を全行読む（最優先）
2. `references/style-guide.md` を読む（ルールの確認）
3. 選択したテンプレートを読む（構成の参考）

**なぜこのステップが重要か**: 抽象的なルール（「カードベースで」「ミント背景で」）よりも、448行の具体的な実装を読んだほうが、フォントサイズ、余白、色の組み合わせ、HTMLの書き方を正確に再現できる。ルールだけでは伝わらない「ちょうどいい情報密度」や「レイアウトのバランス」がこのファイルに詰まっている。

### 3. アウトライン作成

トピックとターゲットに基づいてスライド構成を決定。
- 共感（困りごと）→ 概念説明 → 全体像 → 具体事例 → ステップ詳細 → Tips → 締め
- 身近な例え話を入れて理解を助ける

### 4. Marpマークダウン生成

**フロントマターテンプレート**:
```yaml
---
marp: true
theme: default
paginate: true
header: ''
footer: ''
style: |
  section {
    font-family: 'Hiragino Sans', 'Noto Sans JP', sans-serif;
    background-color: #ffffff;
    padding: 50px 60px;
  }
  header { display: none; }
  h1 { font-size: 44px; color: #1f2937; font-weight: 800; margin-bottom: 16px; line-height: 1.3; }
  h2 { font-size: 32px; color: #374151; font-weight: 700; margin-bottom: 16px; }
  h3 { font-size: 26px; color: #4b5563; font-weight: 600; margin-bottom: 12px; }
  p, li { font-size: 22px; line-height: 1.7; color: #374151; }
  ul, ol { margin-left: 24px; }
  li { margin-bottom: 8px; }
  strong { color: #1f2937; font-weight: 700; }
  blockquote { border-left: 4px solid #028090; padding-left: 16px; margin: 16px 0; color: #4b5563; font-size: 22px; }
---
```

フロントマター直後に Tailwind CSS を読み込む:
```html
<script src="../theme/js/tailwindcss-3.0.16.js"></script>
<script src="../theme/js/tailwind.config.js"></script>
```

**デザインアプローチ**:
- インラインHTML + CSS styleで精密にレイアウト（Tailwindクラスに依存しない）
- カードベースデザイン: 情報を角丸パネルで囲む
- `display: grid; grid-template-columns: 1fr 1fr;` で2カラムレイアウト
- `display: flex; flex-direction: column; gap: 14px;` でカード縦並び
- SVG図解: 比較図、フロー図、サイクル図は `images/` にSVGファイルとして作成
- レイアウトパターンは `references/style-guide.md` の7パターンから選択

**カラー**: Teal Trust パレット
- プライマリ: `#028090` / セカンダリ: `#00A896` / アクセント: `#02C39A`
- ミント背景: `#f0fdf9` / ニュートラル背景: `#f9fafb` / 課題背景: `#fef2f2`
- グラデーションはタイトルと締めスライドのみ

### 5. SVG図解の作成

概念の比較、フロー、サイクルを伝える場面では自作SVGを作成する:
- `slides/images/` に保存
- `viewBox` でサイズ指定、`font-family: 'Hiragino Sans', 'Noto Sans JP', sans-serif`
- Teal Trustカラーで統一
- `<img>` タグで埋め込み: `<img src="images/xxx.svg" style="width: 100%; max-height: 400px; object-fit: contain;">`

### 6. コンテンツ制限チェック（必須）

| コンテンツタイプ | 上限 |
|----------------|------|
| カード（1スライド） | 3-4枚 |
| 箇条書き | 6項目（2階層なら4項目） |
| テーブル | 5行x4列 |
| コードブロック | 8行（コード+説明なら6行） |

### 7. 禁止事項チェック（必須）

- タイトルにコロン禁止
- 感嘆符禁止
- 本文に疑問符禁止（Q&A除く）
- 装飾的な絵文字禁止（✅❌⚠️のみ許可）
- 派手な色禁止（Teal Trust + グレースケールのみ）
- 白文字 on 濃色背景のカード禁止（タイトル・締めスライド以外）
- グラデーション背景カード禁止（タイトル・締めスライド以外）

### 8. ファイル保存

```
スライド: ./slides/{topic}-{date}.md
SVG画像: ./slides/images/{name}.svg
```

### 9. オーディエンス視点セルフレビュー（必須・5ラウンド）

スライド初稿を保存したら、対象者の立場でレビュー→修正を5回繰り返す。

**ペルソナ設定**: 要件収集で確認した「対象者」を具体的に1人設定する。

| ラウンド | 観点 | チェック内容 |
|---------|------|------------|
| 1 | **用語** | 対象者が知らない専門用語・略語はないか |
| 2 | **具体性** | 抽象的な説明を対象者の業務に具体化できるか |
| 3 | **心理的ハードル** | 「難しそう」と感じさせる表現はないか |
| 4 | **流れと分量** | スライド間の論理的つながりは自然か |
| 5 | **総合** | 「結局何をすればいい」が明確か |

### 10. レポート

使用テンプレート、スライド数、保存先、セルフレビュー結果、プレビューコマンドを報告:
```
npx @marp-team/marp-cli ./slides/{filename}.md -o ./slides/preview.html --html
```

## 整合性チェックリスト

- [ ] フロントマターに `marp: true` あり
- [ ] Tailwind CSS scriptタグあり（パスが正しいか確認）
- [ ] スライド区切り `---` の前後に空行あり
- [ ] カラーがTeal Trust + グレースケールのみ
- [ ] コンテンツ量が上限内
- [ ] 禁止事項に違反なし
- [ ] SVG画像は `slides/images/` に保存
- [ ] リファレンス実装と同等の品質か

## 関連ファイル

| ファイル | 内容 |
|---------|------|
| `slides/vibe-coding-intro-20260402.md` | リファレンス実装（品質基準） |
| `references/style-guide.md` | デザインルール・レイアウトパターン |
| `references/marp-syntax.md` | Marp設定・構文 |
| `references/emoji-usage.md` | 絵文字制限 |
| `templates/` | 3種のテンプレート |
| `LAYOUT-FIX.md` | レイアウト検証スキル |
