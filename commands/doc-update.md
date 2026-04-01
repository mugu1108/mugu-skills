# /doc-update - 仕様書同期コマンド

**説明**: コード変更や仕様変更時に `docs/` 配下の仕様書を自動的に同期更新する。

## 使用方法

```
/doc-update [変更内容の説明（省略可）]
```

## いつ使うか

- Bot の機能追加・変更・削除後
- Slack コマンドの追加・変更後
- 環境変数やデータスキーマの変更後

## 使用例

### 例: expense-tracker の変更後

```
/doc-update expense-tracker に delete コマンドを追加した
```

→ `docs/expense-tracker-spec.md` の機能要件セクションを自動更新

省略すると git diff から変更を自動検出:

```
/doc-update
```

## 詳細情報

詳細は [skills/doc-update/SKILL.md](../skills/doc-update/SKILL.md) を参照。
