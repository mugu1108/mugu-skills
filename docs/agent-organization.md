# エージェント体制図

## 概要

mugu-orchestrationはハイブリッド型エージェント組織を採用。統括層（Orchestrator）の下に、機能別チームを配置しています。

**現在のエージェント数: 11体**

---

## 体制図（Mermaid）

```mermaid
flowchart TB
    subgraph Orchestration["統括層"]
        orchestrator["Orchestrator<br/>タスク振り分け"]
    end

    subgraph Development["開発チーム（6体）"]
        architect["Architect<br/>設計（内部）"]
        implementer["Implementer<br/>実装（内部）"]
        test-gen["Test Generator<br/>テスト生成（内部）"]
        code-reviewer["Code Reviewer<br/>コード品質"]
        security-reviewer["Security Reviewer<br/>セキュリティ"]
        doc-updater["Doc Updater<br/>ドキュメント"]
    end

    subgraph Business["ビジネスチーム（3体）"]
        time-tracker["Time Tracker<br/>時間追跡"]
        daily-briefing["Daily Briefing<br/>朝のブリーフィング"]
        expense-tracker["Expense Tracker<br/>経費記録"]
    end

    subgraph Content["コンテンツチーム（1体）"]
        slide-creator["Slide Creator<br/>スライド生成"]
    end

    orchestrator --> Development
    orchestrator --> Business
    orchestrator --> Content

    architect --> implementer
    implementer --> test-gen
    test-gen --> code-reviewer
```

---

## ディレクトリ構成

```
agents/
├── orchestrator.md              # 統括エージェント
│
├── development/                 # 開発チーム（6体）
│   ├── architect.md            # 設計・技術選定
│   ├── implementer.md          # コード実装
│   ├── test-generator.md       # テスト生成
│   ├── code-reviewer.md        # コード品質レビュー
│   ├── security-reviewer.md    # セキュリティレビュー
│   └── doc-updater.md          # ドキュメント更新
│
├── business/                    # ビジネスチーム（3体）
│   ├── time-tracker.md         # 時間追跡
│   ├── daily-briefing.md       # デイリーブリーフィング
│   └── expense-tracker.md      # 経費記録
│
└── content/                     # コンテンツチーム（1体）
    └── slide-creator.md        # スライド生成
```

---

## チーム別エージェント一覧

### 統括層（1体）

| エージェント | 役割 | モデル |
|-------------|------|--------|
| **Orchestrator** | タスク振り分け、チーム間調整 | Sonnet |

### 開発チーム（6体）

| エージェント | 役割 | モデル | コマンド |
|-------------|------|--------|---------|
| **Architect** | 設計・技術選定（内部） | Opus | - |
| **Implementer** | コード実装（内部） | Opus | - |
| **Test Generator** | テスト提案・生成（内部） | Sonnet | - |
| **Code Reviewer** | コード品質レビュー | Sonnet | `/code-review` |
| **Security Reviewer** | セキュリティ分析 | Opus | - |
| **Doc Updater** | ドキュメント更新 | Sonnet | - |

### ビジネスチーム（3体）

| エージェント | 役割 | プラットフォーム | コマンド |
|-------------|------|-----------------|---------|
| **Time Tracker** | 作業時間記録 | Slack Bot | `/in`, `/out`, `/status`, `/today`, `/week`, `/undo`, `/project` |
| **Daily Briefing** | 朝の情報まとめ | Slack Bot | `/briefing` |
| **Expense Tracker** | 経費記録・税務相談 | Slack Bot | `add`, `summary`, `list`, `search`, `delete`, `help` |

### コンテンツチーム（1体）

| エージェント | 役割 | モデル | コマンド |
|-------------|------|--------|---------|
| **Slide Creator** | Marpスライド生成 | Sonnet | `/slide` |

---

## 開発フロー

```
設計依頼
    │
    ▼
Architect（設計・技術選定）
    │
    ▼
Implementer（コード実装）
    │
    ▼
Test Generator（テスト提案・生成）
    │
    ▼
Code Reviewer（コード品質レビュー）
    │
    ├──→ Security Reviewer（セキュリティ懸念がある場合）
    │
    ▼
Doc Updater（ドキュメント更新）
    │
    ▼
完了
```

---

## 内部エージェント

以下は直接コマンド呼び出しではなく、Orchestratorからの委譲で動作する内部エージェントです:

- **Architect** - 設計タスクをOrchestratorが委譲
- **Implementer** - 実装タスクをOrchestratorが委譲
- **Test Generator** - テスト生成をCode Reviewerが委譲
