# スライドスタイルガイド

デザインルール統合ドキュメント。カラー、タイポグラフィ、レイアウトパターン、禁止事項を定義。

**リファレンス実装**: `slides/vibe-coding-intro-20260402.md` を品質基準とする。

---

## デザイン哲学

1. **1スライド1メッセージ** - 各スライドは1つの概念だけを伝える
2. **インラインHTML + CSS** - Tailwindクラスではなくインラインstyleで精密にレイアウト
3. **カードベースデザイン** - 情報をカード（角丸パネル）で囲み視認性を高める
4. **SVG図解** - 比較図・フロー図・サイクル図は自作SVGで表現
5. **色で意味を伝える** - ミント=ポジティブ/強調、ピンク=課題/問題、グレー=ニュートラル

---

## カラーパレット（Teal Trust）

### プライマリカラー

| 色名 | コード | 用途 |
|------|--------|------|
| **ティール** | `#028090` | プライマリ。見出し、ボーダー、ラベル、ボタン |
| **ミドルティール** | `#00A896` | セカンダリ。アクセント、2色目のボーダー |
| **グリーンティール** | `#02C39A` | 3色目。グラデーション終端、3番目のアクセント |

### 背景カラー

| 色名 | コード | 用途 |
|------|--------|------|
| **ミント** | `#f0fdf9` | 強調カード背景、ポジティブな情報 |
| **ニュートラル** | `#f9fafb` | 一般カード背景、コンテンツパネル |
| **ピンク** | `#fef2f2` | 課題・問題を示すカード |
| **白** | `#ffffff` | スライド背景、カード内の子要素 |

### テキストカラー

| 色名 | コード | 用途 |
|------|--------|------|
| **ダーク** | `#1f2937` | メインテキスト、太字 |
| **ミディアム** | `#374151` | 本文テキスト |
| **ライト** | `#6b7280` | 補助テキスト、サブ説明 |
| **ペール** | `#9ca3af` | 最小限の注釈 |
| **ティール** | `#028090` | カテゴリラベル、強調テキスト |
| **レッド** | `#991b1b` | 課題・問題のラベル |

### グラデーション（タイトル・締めスライドのみ）

```css
background-image: linear-gradient(135deg, #028090 0%, #00A896 50%, #02C39A 100%);
color: #fff;
```

### 使用禁止カラー

`red-600`, `green-600`, `blue-600`, `yellow-500` — 派手すぎる。強調は `font-weight: 700` + `color: #028090` で表現。

---

## タイポグラフィ

インラインstyleで指定。Tailwindの `text-em-*` は使わない。

| 用途 | サイズ | Weight | Color |
|------|--------|--------|-------|
| H1（スライドタイトル） | `44px` | `800` | `#1f2937` |
| H2（セクション） | `32px` | `700` | `#374151` |
| H3（サブ） | `26px` | `600` | `#4b5563` |
| 本文・リスト | `22px` | — | `#374151` |
| カード内テキスト | `18-20px` | — | `#374151` |
| カテゴリラベル | `15-16px` | `700` | `#028090` |
| 補助説明 | `17px` | — | `#6b7280` |

---

## レイアウトパターン

### 1. 強調カード（ミント背景 + ティールボーダー）

結論やキーメッセージに使用。

```html
<div style="background: #f0fdf9; border: 2px solid #028090; border-radius: 16px; padding: 24px; text-align: center;">
  <p style="font-size: 24px; font-weight: 700; color: #028090;">キーメッセージ</p>
  <p style="font-size: 20px; color: #374151; margin-top: 6px;">補足説明</p>
</div>
```

### 2. コンテンツカード（グレー背景）

一般的な情報の列挙に使用。

```html
<div style="background: #f9fafb; border-radius: 12px; padding: 18px 24px; border-left: 4px solid #d1d5db;">
  <p style="font-size: 21px; color: #374151;">コンテンツ</p>
</div>
```

### 3. 課題カード（ピンク背景）

問題点や困りごとに使用。

```html
<div style="background: #fef2f2; border-radius: 10px; padding: 14px 18px;">
  <p style="font-size: 18px; color: #374151;">課題の説明</p>
</div>
```

### 4. 2カラムグリッド

対比や左右の情報整理に使用。

```html
<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div>左カラム</div>
  <div>右カラム</div>
</div>
```

### 5. カテゴリラベル

カードの先頭に小さな色付きラベルを配置。

```html
<p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 10px;">カテゴリ名</p>
```

### 6. 左ボーダーアクセント付きリスト

段階や種類を色分けで示す。

```html
<div style="background: #f9fafb; border-radius: 10px; padding: 12px 16px; border-left: 3px solid #028090;">
  <p style="font-size: 17px; color: #374151;">項目1</p>
</div>
<div style="background: #f9fafb; border-radius: 10px; padding: 12px 16px; border-left: 3px solid #00A896;">
  <p style="font-size: 17px; color: #374151;">項目2</p>
</div>
```

### 7. 会話UI

AIとの対話を視覚的に表現。

```html
<div style="display: flex; align-items: center; gap: 12px;">
  <span style="background: #e5e7eb; border-radius: 8px; padding: 4px 10px; font-size: 13px; font-weight: 700; color: #6b7280;">あなた</span>
  <div style="background: white; border-radius: 12px; padding: 12px 16px; box-shadow: 0 1px 3px rgba(0,0,0,0.08); flex: 1;">
    <p style="font-size: 18px; color: #374151;">ユーザーの発言</p>
  </div>
</div>
<div style="display: flex; align-items: center; gap: 12px;">
  <span style="background: #028090; border-radius: 8px; padding: 4px 10px; font-size: 13px; font-weight: 700; color: white;">AI</span>
  <div style="background: #f0fdf9; border-radius: 12px; padding: 12px 16px; flex: 1;">
    <p style="font-size: 18px; color: #374151;">AIの応答</p>
  </div>
</div>
```

---

## コンテンツ制限

| コンテンツタイプ | 上限 |
|----------------|------|
| カード（1スライド内） | **3-4枚** |
| 箇条書き | **6項目**（2階層なら4項目） |
| テーブル | **5行 x 4列** |
| コードブロック | **8行**（コード+説明なら6行） |
| 段落テキスト | **2-3段落** |

9行以上のコードは分割必須。命名: 「実装（1/3）」

---

## 禁止事項

1. **タイトルにコロン禁止** — `原則: 自律性` → `原則 自律性`
2. **感嘆符禁止** — 全スライドで `!` を使わない
3. **疑問符禁止**（Q&Aスライド除く）
4. **装飾的な絵文字禁止** — 状態アイコン ✅❌⚠️ のみ許可
5. **派手な色禁止** — Teal Trust + グレースケールのみ
6. **白文字 on 濃色背景のカード禁止** — 可読性が低い。ミント背景+濃色テキストを使う
7. **グラデーション背景カード禁止** — タイトル・締めスライド以外でのグラデーション使用は不可
