# /expense-track - 経費記録Bot

**説明**: レシート画像やテキストから経費を自動解析し、Google Sheetsに記録するSlack Bot。

## 使用方法

```bash
# Bot起動
npm run expense-tracker

# Slackコマンド
@expensebot [レシート画像]              # 画像OCR解析
@expensebot add [内容]                 # テキスト経費入力
@expensebot summary                    # スプレッドシートリンク
@expensebot help                       # ヘルプ表示
```

## 概要

Gemini Flash APIでレシート画像をOCR解析し、勘定科目を自動判定してGoogle Sheetsに記録する経費管理Bot。確認ボタンで人間がチェックしてから保存する半自動設計。

## いつ使うか

- レシートを受け取ったとき、すぐにSlackで経費登録したい
- 確定申告の経費管理を効率化したい
- テキストで簡単に経費を記録したい

## 使用例

### 例1: レシート画像からの経費登録

入力:
```
@expensebot [レシート画像を添付]
```

出力:
```
経費を登録しますか？
📅 日付: 2026-02-28
💰 金額: ¥550
📝 摘要: スターバックス コーヒー
📂 勘定科目: 接待交際費
💳 支払方法: 電子マネー
🧾 税区分: 8%対象（軽減）
[✅ 保存] [✏️ 修正] [❌ キャンセル]
```

### 例2: テキストからの経費登録

入力:
```
@expensebot add Amazon 技術書 3200円
```

## 関連エージェント

- **Expense Tracker**: 経費記録エージェント（`agents/business/expense-tracker.md`）

## 詳細情報

- ワークフロー詳細: `skills/expense-track/SKILL.md`
