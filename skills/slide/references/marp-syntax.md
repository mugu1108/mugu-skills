# Marp構文リファレンス（プロジェクト固有）

標準的なMarkdown構文は省略。プロジェクト固有の設定とインラインHTMLパターンを記載。

---

## フロントマターテンプレート

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

<script src="../theme/js/tailwindcss-3.0.16.js"></script>
<script src="../theme/js/tailwind.config.js"></script>
```

---

## グラデーション背景（タイトル・締めスライドのみ）

```markdown
<!-- _class: lead -->
<!-- _paginate: false -->
<!--
_backgroundImage: "linear-gradient(135deg, #028090 0%, #00A896 50%, #02C39A 100%)"
_color: #fff
-->

<div style="text-align: center;">

# タイトル

<p style="font-size: 28px; opacity: 0.9; margin-top: 24px;">サブタイトル</p>
<p style="font-size: 20px; opacity: 0.7; margin-top: 40px;">日付 ｜ イベント名</p>

</div>
```

---

## レイアウトディレクティブ

| ディレクティブ | 効果 |
|---------------|------|
| `<!-- _class: lead -->` | 中央揃え（タイトル・締め用） |
| `<!-- _paginate: false -->` | ページ番号非表示 |

---

## SVG図解の埋め込み

SVGは `slides/images/` に保存し、`<img>` タグで表示:

```html
<img src="images/diagram-name.svg" style="width: 100%; max-height: 400px; object-fit: contain;">
```

### SVGテンプレート

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 340"
     font-family="'Hiragino Sans', 'Noto Sans JP', sans-serif">
  <!-- Teal Trustカラーを使用: #028090, #00A896, #02C39A -->
</svg>
```

---

## スライド区切り

`---` の前後に**必ず空行**が必要:

```markdown
# スライド1

---

# スライド2
```

---

## HTMLビルドとプレビュー

```bash
# HTML生成（slides/ ディレクトリで実行）
npx @marp-team/marp-cli {filename}.md -o preview.html --html

# ローカルサーバーでプレビュー（SVG画像の相対パスを解決するため）
npx http-server . -p 8080
```
