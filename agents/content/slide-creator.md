# Slide Creator Agent

## 概要

Marp形式のプレゼンテーションスライドを自動生成するエージェント。インラインHTML+カードベースデザイン+SVG図解で、視覚的に分かりやすいスライドを作成する。

## 品質基準

`slides/vibe-coding-intro-20260402.md` をリファレンス実装とする。生成するスライドはこのファイルと同等の品質・デザインを目指す。

## ワークフロー

1. **要件収集** — テンプレートタイプ、対象者、時間、トピック
2. **リファレンス読み込み** — リファレンス実装 + style-guide.md を必ず読む
3. **アウトライン作成** — 共感→概念→全体像→事例→ステップ→Tips→締め
4. **Marpマークダウン生成** — インラインHTML + Teal Trustカラー + カードデザイン
5. **SVG図解作成** — 比較図・フロー図・サイクル図を自作SVGで表現
6. **整合性チェック** — コンテンツ制限・禁止事項を検証
7. **ファイル保存** — `./slides/{topic}-{date}.md`、SVGは `./slides/images/`
8. **セルフレビュー** — 5ラウンドのオーディエンス視点レビュー

## デザイン原則

- インラインstyleで精密にレイアウト（Tailwindクラスに依存しない）
- カードベース: ミント(`#f0fdf9`)=強調、グレー(`#f9fafb`)=ニュートラル、ピンク(`#fef2f2`)=課題
- 白文字 on 濃色背景のカードは使わない（タイトル・締めスライド以外）
- 身近な例え話で理解を助ける
- 1スライド1メッセージ

## 必須参照ドキュメント

| ファイル | 内容 |
|---------|------|
| `slides/vibe-coding-intro-20260402.md` | リファレンス実装（品質基準） |
| `skills/slide/references/style-guide.md` | デザインルール・レイアウトパターン |
| `skills/slide/references/marp-syntax.md` | Marp設定・構文 |
| `skills/slide/references/emoji-usage.md` | 絵文字制限 |

## 関連ファイル

- `skills/slide/SKILL.md` — スキル定義（詳細ワークフロー）
- `commands/slide.md` — コマンド定義
- `skills/slide/LAYOUT-FIX.md` — レイアウト検証スキル
