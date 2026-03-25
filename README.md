# SidekiX Resume

[![SidekiX](https://img.shields.io/badge/SidekiX-Resume-0284c7?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0id2hpdGUiPjxwYXRoIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0wIDE4Yy00LjQxIDAtOC0zLjU5LTgtOHMzLjU5LTggOC04IDggMy41OSA4IDgtMy41OSA4LTggNHoiLz48L3N2Zz4=)](https://sidekix.jp)

> GitHub x AI - あなたのキャリアをコードで管理する

**[公開レジュメを見る](https://sidekix.jp/u/USERNAME)** | **[PDF ダウンロード](https://sidekix.jp/u/USERNAME/pdf)**

---

## About

このリポジトリは [SidekiX](https://sidekix.jp) と連携するレジュメリポジトリです。
Markdownファイルを編集してpushするだけで、レジュメページが自動生成されます。

- プロフィール・スキル・希望条件をMarkdownで管理
- プロジェクト実績と経歴を個別ファイルで管理
- GitHub push で自動同期 -- 手動操作は不要
- Claude Code で AI 編集に対応

## Quick Start

### 1. テンプレートからリポジトリを作成

> 「Use this template」をクリック

### 2. SidekiX で GitHub 連携を設定

> [sidekix.jp](https://sidekix.jp) にログイン → 設定 → GitHub連携 → リポジトリを選択

### 3. ファイルを編集して push

> `profile.md`, `skills.md`, `wish.md` を書き換え、`projects/` と `histories/` にファイルを追加

```
sidekix.jp/u/{username} であなたのレジュメが公開されます
```

## File Structure

```
profile.md              プロフィール（名前・ポジション・サマリー）
skills.md               スキル一覧（言語・FW・サービス）
wish.md                 希望条件（稼働・年収・勤務地）
projects/
  _template.md          プロジェクトのテンプレート
  *.md                  プロジェクト実績
histories/
  _template.md          経歴のテンプレート
  *.md                  経歴
.sidekix/
  schema.json           フィールド定義（JSON Schema）
CLAUDE.md               AI編集仕様書
```

## Claude Code Usage

このリポジトリは [Claude Code](https://docs.anthropic.com/en/docs/claude-code) での編集に対応しています。
`CLAUDE.md` にfrontmatter仕様が記載されているため、自然言語で指示するだけで正しいフォーマットのファイルが生成されます。

```bash
claude "プロフィールを更新して。ポジションはバックエンドエンジニアに変更"

claude "新しいプロジェクト「API Gateway構築」を追加して。Go + AWS、チーム4人、テックリード"

claude "経歴にフリーランス期間（2019-04〜2021-03）を追加して"

claude "スキルにKubernetesとTerraformを追加して"

claude "希望条件をリモートワーク希望に更新して"
```

## Frontmatter Reference

各ファイルのfrontmatter仕様の詳細は [`CLAUDE.md`](./CLAUDE.md) を参照してください。
JSON Schema による型定義は [`.sidekix/schema.json`](./.sidekix/schema.json) に格納されています。

## License

MIT
