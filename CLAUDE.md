# mugu-skills

Claude Code 用のスキル・コマンド・エージェント集。

## 構成

```
skills/      # スキル定義（ワークフロー・ロジック）
commands/    # スラッシュコマンドUI定義
agents/      # エージェント定義（チーム構成）
rules/       # 汎用コーディングルール
```

## スキル一覧

| コマンド | スキル | 用途 |
|---------|--------|------|
| `/code-review` | code-review | コード品質チェック |
| `/slide` | slide | Marpスライド生成 |
| `/security-review` | security-review | セキュリティ監査 |
| `/doc-update` | doc-update | docs/ 仕様書の自動同期 |
| `/md-review` | md-review | MD品質チェック |
| `/time-track` | time-track | 時間追跡 |
| `/expense-track` | expense-track | 経費記録 |
| `/lp` | lp | クリップボード長文ペースト |
| `/learn` | learn | セッションからパターン抽出・保存 |
| `/context-budget` | context-budget | コンテキスト消費量分析・節約提案 |
| `/strategic-compact` | strategic-compact | 戦略的コンテキスト圧縮 |
| `/codebase-onboarding` | codebase-onboarding | 新リポの構造分析・CLAUDE.md生成 |
| `/security-scan` | security-scan | Claude Code 設定のセキュリティスキャン |
| `/coding-standards` | coding-standards | TS/React/Node.js コーディング規約 |
| `/rules-distill` | rules-distill | スキルからルールを抽出 |
| `/git-workflow` | git-workflow | Git ブランチ戦略・コミット規約 |
| `/repo-scan` | repo-scan | リポジトリ資産監査 |
| `/autonomous-agent` | autonomous-agent-harness | 自律型エージェント構築（定期実行・監視） |
| `/skill-stocktake` | skill-stocktake | スキル品質監査 |
| `/data-scraper` | data-scraper-agent | 無料スタックのデータ収集エージェント |
| `/workspace-audit` | workspace-surface-audit | Claude Code 環境診断・最適化 |

## 利用方法

### スタンドアロン

このリポジトリを直接 Claude Code プラグインとして登録。

### サブモジュール

他プロジェクトから git submodule で参照：

```bash
git submodule add https://github.com/mugu1108/mugu-skills.git mugu-skills
```

plugin.json でパスを指定：

```json
{
  "commands": "./mugu-skills/commands",
  "skills": "./mugu-skills/skills",
  "agents": "./mugu-skills/agents",
  "rules": "./mugu-skills/rules"
}
```
