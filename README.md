# SidekiX Resume Template

[SidekiX](https://sidekix.jp) でエンジニアのレジュメを管理するためのテンプレートリポジトリです。

## セットアップ

1. **このテンプレートからリポジトリを作成**
   - 「Use this template」ボタンをクリック
   - リポジトリ名を自由に設定（例: `my-resume`）

2. **SidekiXでGitHub連携を設定**
   - [sidekix.jp](https://sidekix.jp) にログイン
   - 設定 → GitHub連携 からGitHub Appをインストール
   - 作成したリポジトリを選択

3. **ファイルを編集してpush**
   - `profile.md` を自分の情報に書き換え
   - `skills.yml` にスキルを記載
   - `projects/` にプロジェクト実績を追加
   - `histories/` に経歴を追加

4. **レジュメを確認**
   - `sidekix.jp/u/{username}` で公開レジュメを確認

## ファイル構造

```
├── profile.md          # プロフィール情報（名前、ポジション、経歴概要）
├── skills.yml          # スキル一覧（言語・フレームワーク・サービス）
├── projects/           # プロジェクト実績
│   ├── fintech-payment.md
│   └── ec-site-renewal.md
├── histories/          # 経歴
│   ├── acme-corp.md
│   └── startup-freelance.md
├── CLAUDE.md           # Claude Code用のfrontmatter仕様書
└── README.md           # このファイル
```

## frontmatter仕様

各ファイルの詳しいfrontmatter仕様は [CLAUDE.md](./CLAUDE.md) を参照してください。

## Claude Codeで編集

このリポジトリは [Claude Code](https://claude.ai/claude-code) での編集に最適化されています。
`CLAUDE.md` にfrontmatter仕様が記載されているため、Claude Codeが自動的にフォーマットに従ったファイルを生成します。

```bash
# Claude Codeでの操作例
claude "新しいプロジェクト「API Gateway構築」を追加して"
claude "経歴にフリーランス期間を追加して"
claude "スキルにKubernetesを追加して"
```

## ライセンス

このテンプレートはMITライセンスです。自由にご利用ください。
