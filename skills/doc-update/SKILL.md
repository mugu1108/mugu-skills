---
name: doc-update
description: コード変更や仕様変更時に docs/ 配下の仕様書を自動的に同期更新する
category: documentation
triggers:
  - "doc-update"
  - "ドキュメント更新"
  - "仕様書更新"
  - "update docs"
tools:
  - Read
  - Edit
  - Write
  - Grep
  - Glob
  - Bash
---

# /doc-update - 仕様書同期コマンド

**説明**: コード変更や仕様変更時に `docs/` 配下の仕様書を自動的に同期更新する。

## 使用方法

```
/doc-update [変更内容の説明（省略可）]
```

## 概要

プロジェクトの `docs/` ディレクトリにある仕様書を、実装コード（`src/`）や設定の変更と同期させる。変更内容の説明が省略された場合は `git diff` から変更を自動検出する。

## 起動タイミング

- Bot の機能追加・変更・削除後
- Slack コマンドの追加・変更後
- 環境変数やデータスキーマの変更後
- 外部サービス連携（freee, Google API等）の変更後

## 前提条件

- `docs/` ディレクトリに仕様書が存在する
- 仕様書はマークダウン形式

## 対象ドキュメントとコードの対応表

| ドキュメント | 対応コード | 主な記載内容 |
|-------------|-----------|-------------|
| `docs/time-tracker-spec.md` | `src/bots/time-tracker/`, `src/modules/time-tracker/` | Slackコマンド、データ設計、Supabase連携 |
| `docs/expense-tracker-spec.md` | `src/bots/expense-tracker/`, `src/modules/expense-tracker/` | OCR処理、freee連携、勘定科目、税務相談 |
| `docs/daily-briefing-spec.md` | `src/bots/daily-briefing/`, `src/modules/daily-briefing/` | 自動投稿スケジュール、情報ソース |
| `docs/lessons.md` | （全体） | セッション中の教訓・パターン集 |

## ワークフローステップ

### ステップ1: 変更検出

変更内容を特定する:

- ユーザーが説明を提供 → その内容を使用
- 省略された場合 → `git diff HEAD` と `git log --oneline -5` から変更を検出

### ステップ2: 影響範囲の特定

変更されたコードパスから影響を受ける仕様書を特定:

- `src/bots/time-tracker/` or `src/modules/time-tracker/` → `docs/time-tracker-spec.md`
- `src/bots/expense-tracker/` or `src/modules/expense-tracker/` → `docs/expense-tracker-spec.md`
- `src/bots/daily-briefing/` or `src/modules/daily-briefing/` → `docs/daily-briefing-spec.md`

### ステップ3: コードと仕様書の比較

影響を受ける仕様書を Read で読み込み、実装コードと突き合わせる:

- Slack コマンド名・引数が一致しているか
- 環境変数一覧が最新か
- データスキーマ（テーブル定義等）が反映されているか
- 処理フローの記述が実装と合っているか

### ステップ4: 仕様書の更新

差分がある箇所のみ Edit で更新する:

- 既存の文書構造・トーンを維持
- 新しいセクションが必要な場合のみ追加
- 不要になったセクションは削除ではなく「廃止」と注記

### ステップ5: 更新レポート

更新内容をユーザーに報告:

```markdown
## 仕様書更新レポート

### 更新対象
- docs/expense-tracker-spec.md

### 変更内容
- 環境変数一覧に `FREEE_COMPANY_ID` を追加
- 処理フローにバリデーションステップを追記

### 未更新（要確認）
- （手動確認が必要な項目があれば記載）
```

## 使用例

### 例1: expense-tracker に新しいコマンドを追加した後

```
/doc-update expense-tracker に delete コマンドを追加した
```

→ `docs/expense-tracker-spec.md` の機能要件セクションに delete コマンドの仕様を追記

### 例2: 変更内容を自動検出

```
/doc-update
```

→ git diff から変更ファイルを検出し、関連する仕様書を自動更新

## ベストプラクティス

1. 機能実装の直後に実行し、仕様書の乖離を最小限に保つ
2. 大きな機能追加時は変更内容を明示的に説明する方が精度が上がる
3. lessons.md への追記はこのスキルではなく手動で行う

## 関連エージェント

- **doc-updater**: このコマンドが呼び出すエージェント（`agents/development/doc-updater.md`）

## モデル選択

- **Sonnet**: 通常の仕様書更新（コマンド追加、環境変数更新等）
- **Opus**: 大規模な仕様変更やアーキテクチャ変更の反映

## 注意事項

- 仕様書の「目的」「概要」セクションはビジネス判断を含むため、自動更新せず変更提案のみ行う
- lessons.md は追記専用。既存の教訓を編集・削除しない
