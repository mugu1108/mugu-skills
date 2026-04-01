---
name: expense-track
description: レシート画像やテキストからAIで経費を自動解析し、Google Sheetsに記録するSlack Bot
category: workflow
triggers:
  - "expense tracking"
  - "経費記録"
  - "レシート解析"
tools:
  - Read
  - Glob
  - Bash
---

# /expense-track - 経費記録Bot

**説明**: レシート画像のOCRまたはテキスト入力から経費を自動解析し、確認後にGoogle Sheetsに記録する。

## 使用方法

```bash
# Bot起動
npm run expense-tracker

# Slackでの使用
@expensebot [レシート画像]          # 画像OCR
@expensebot add スタバ コーヒー 550円  # テキスト入力
@expensebot summary                # スプシリンク
@expensebot help                   # ヘルプ
```

## 概要

Gemini Flash APIでレシート画像をOCR解析し、勘定科目（11種類）を自動判定。Slack Block Kitの確認ボタンで人間がチェックした後、Google Sheetsに記録する。青色申告のフリーランス向け。

## 起動タイミング

- レシートを受け取ったとき
- 経費をすぐに記録したいとき
- 確定申告の経費管理

## 前提条件

- Slack App（Socket Mode、`app_mention` + `files:read` スコープ）
- Gemini API Key
- Google OAuth 2.0（Sheets権限付き）
- Google Spreadsheet

## ワークフローステップ

### ステップ1: 入力受付
画像付きメンション → OCR解析、テキストメンション → テキスト解析

### ステップ2: Gemini解析
日付、金額、摘要、勘定科目、支払方法、税区分を自動判定

### ステップ3: 確認表示
Block Kit ボタン付きメッセージで確認（✅保存 / ✏️修正 / ❌キャンセル）

### ステップ4: 修正（任意）
スレッド返信で `科目 通信費` のように部分修正

### ステップ5: 保存
Google Sheets APIで経費データを追記

## 使用例

### 例1: レシート画像から経費登録

```
@expensebot [レシート画像]
→ 解析結果を確認メッセージで表示
→ ✅ 保存でスプレッドシートに記録
```

## 関連エージェント

- **Expense Tracker**: 経費記録エージェント（`agents/business/expense-tracker.md`）

## 環境変数

| 変数 | 説明 |
|------|------|
| `EXPENSE_BOT_TOKEN` | Slack Bot Token |
| `EXPENSE_APP_TOKEN` | Slack App Token |
| `GOOGLE_GENAI_API_KEY` | Gemini API Key |
| `EXPENSE_SHEET_ID` | スプレッドシートID |
| `EXPENSE_SHEET_NAME` | シート名（デフォルト: 経費記録） |
| `GOOGLE_CLIENT_ID` | Google OAuth Client ID |
| `GOOGLE_CLIENT_SECRET` | Google OAuth Client Secret |
| `GOOGLE_REFRESH_TOKEN` | Google OAuth Refresh Token |
