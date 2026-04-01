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
| `/plan` | plan | 実装計画作成 |
| `/code-review` | code-review | コード品質チェック |
| `/slide` | slide | Marpスライド生成 |
| `/security-review` | security-review | セキュリティ監査 |
| `/doc-update` | doc-update | ドキュメント同期 |
| `/md-review` | md-review | MD品質チェック |
| `/time-track` | time-track | 時間追跡 |
| `/expense-track` | expense-track | 経費記録 |

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
