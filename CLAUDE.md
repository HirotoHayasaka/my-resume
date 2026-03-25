# SidekiX Resume Repository - AI Editing Specification

このファイルは、Claude Code がこのリポジトリを編集する際の仕様書です。
ファイルをpushすると [sidekix.jp](https://sidekix.jp) のレジュメが自動更新されます。

## ファイル構造

```
.
├── profile.md              # プロフィール情報
├── skills.md               # スキル一覧（frontmatterのみ）
├── wish.md                 # 希望条件
├── projects/               # プロジェクト実績
│   ├── _template.md        # テンプレート（pushしてもインポートされない）
│   ├── fintech-payment.md
│   └── ec-site-renewal.md
├── histories/              # 経歴
│   ├── _template.md        # テンプレート（pushしてもインポートされない）
│   ├── acme-corp.md
│   └── startup-freelance.md
├── .sidekix/
│   └── schema.json         # 全フィールドのJSON Schema定義
├── CLAUDE.md               # このファイル（AI編集仕様書）
└── README.md               # ユーザー向け説明
```

## Frontmatter仕様

### profile.md

プロフィール情報。本文はキャリアサマリーとして表示される。

| フィールド | 型 | 必須 | 説明 |
|---|---|---|---|
| `nickname` | string | - | 表示名 |
| `position` | string | - | ポジション |
| `career_started_year` | integer | - | キャリア開始年（YYYY形式） |
| `birth_year` | integer | - | 生年（1940-2010） |
| `education` | string | - | 学歴（自由記述） |
| `profile_image_url` | string (URI) | - | プロフィール画像URL |
| `x_account_url` | string (URI) | - | X（旧Twitter）アカウントURL |

### skills.md

スキル一覧。frontmatterのみで本文は不要。

| フィールド | 型 | 必須 | 説明 |
|---|---|---|---|
| `languages` | array | - | プログラミング言語 |
| `frameworks` | array | - | フレームワーク・ライブラリ |
| `services` | array | - | クラウド・ミドルウェア・SaaS |

各スキルのサブフィールド:

| フィールド | 型 | 必須 | 説明 |
|---|---|---|---|
| `name` | string | **必須** | スキル名 |
| `experience` | enum | - | `half_year` / `1_year` / `2_years` / `3_years` / `over_3_years` |

### wish.md

希望条件。本文にはキャリアの希望・方向性を自由記述。

| フィールド | 型 | 必須 | 説明 |
|---|---|---|---|
| `availability` | enum | - | `fulltime` / `partial` / `sidejob` / `not_available` |
| `desired_annual_income` | integer | - | 希望年収（万円単位） |
| `preferred_locations` | string | - | 希望勤務地（カンマ区切り） |
| `desired_hourly_rate` | integer | - | 希望時給（円単位） |
| `available_hours_per_week` | integer | - | 週あたり稼働可能時間（0-168） |
| `notice_period` | string | - | 退職・参画までの期間 |

### projects/*.md

プロジェクト実績。ファイル名は `kebab-case.md`。

| フィールド | 型 | 必須 | 説明 |
|---|---|---|---|
| `title` | string | **必須** | プロジェクト名 |
| `company` | string | **必須** | 会社名 |
| `status` | enum | - | `draft` / `published`（デフォルト: `published`） |
| `started` | string | - | 開始年月（`YYYY-MM`形式） |
| `ended` | string | - | 終了年月（`YYYY-MM`形式、進行中は省略） |
| `role` | string | - | 担当ロール |
| `team_size` | integer | - | チーム人数（正の整数） |
| `skills` | string[] | - | 使用技術一覧 |

### histories/*.md

経歴。ファイル名は `kebab-case.md`。

| フィールド | 型 | 必須 | 説明 |
|---|---|---|---|
| `company` | string | **必須** | 企業名 |
| `type` | enum | **必須** | `employee` / `freelance` / `sidejob` |
| `position` | string | **必須** | ポジション |
| `from` | string | **必須** | 入社年月（`YYYY-MM`形式） |
| `to` | string | - | 退社年月（`YYYY-MM`形式、在職中は省略） |
| `summary` | string | - | 概要（120文字以内） |
| `skills` | string[] | - | 使用技術一覧 |

## 操作手順

### プロジェクトを追加する

1. `projects/_template.md` をコピーして新しいファイルを作成
2. ファイル名は `kebab-case.md`（例: `api-gateway-development.md`）
3. frontmatterの `title` と `company` を必ず記入
4. 本文に概要・担当・成果を記述

### 経歴を追加する

1. `histories/_template.md` をコピーして新しいファイルを作成
2. ファイル名は `kebab-case.md`（例: `example-corp.md`）
3. frontmatterの `company`, `type`, `position`, `from` を必ず記入
4. 在職中の場合は `to` を省略

### スキルを追加する

1. `skills.md` のfrontmatter内の該当カテゴリに追加
2. カテゴリ: `languages` / `frameworks` / `services`
3. `name` は必須、`experience` は任意

```yaml
# 追加例
languages:
  - name: "Rust"
    experience: "1_year"
```

### プロフィールを編集する

1. `profile.md` のfrontmatterとmarkdown本文を編集
2. 本文はキャリアサマリーとして表示される

### 希望条件を編集する

1. `wish.md` のfrontmatterとmarkdown本文を編集
2. 本文にはキャリアの希望・方向性を自由記述

## バリデーションルール

### 日付形式
- `YYYY-MM` 形式のみ（例: `2024-04`）
- 月は `01` - `12`

### enum値
- **availability**: `fulltime` / `partial` / `sidejob` / `not_available`
- **history type**: `employee` / `freelance` / `sidejob`
- **status**: `draft` / `published`
- **experience**: `half_year` / `1_year` / `2_years` / `3_years` / `over_3_years`

### ファイル名規則
- `kebab-case.md` を使用（例: `fintech-payment.md`）
- 日本語ファイル名は使用しない
- `_template.md` はインポート対象外（テンプレートとして保持）

### 数値制約
- `career_started_year`: 1970-2030
- `birth_year`: 1940-2010
- `available_hours_per_week`: 0-168
- `team_size`: 1以上の正の整数
- `desired_annual_income`: 0以上の整数（万円）
- `desired_hourly_rate`: 0以上の整数（円）

### 文字数制約
- `summary`（history）: 120文字以内

## セルフチェックリスト

ファイルを編集・作成した後、以下を確認すること:

- [ ] frontmatterが `---` で正しく囲まれているか
- [ ] 必須フィールドが全て記入されているか
- [ ] 日付が `YYYY-MM` 形式になっているか
- [ ] enum値が許可された値のいずれかであるか
- [ ] ファイル名が `kebab-case.md` になっているか
- [ ] `skills.md` のスキルに `name` が含まれているか
- [ ] `history` の `from` が `to` より前の日付であるか
- [ ] `project` の `started` が `ended` より前の日付であるか
- [ ] コメントアウトされたフィールド（`#` 付き）が正しいYAML構文か
