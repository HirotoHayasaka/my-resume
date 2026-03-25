# SidekiX Resume Repository

このリポジトリはSidekiX（sidekix.jp）と連携して、エンジニアのレジュメを管理するためのリポジトリです。
ファイルをpushすると自動的にレジュメページが更新されます。

## ファイル構造

```
├── profile.md          # プロフィール情報
├── skills.yml          # スキル一覧
├── projects/           # プロジェクト実績（*.md）
│   └── example.md
├── histories/          # 経歴（*.md）
│   └── example.md
└── CLAUDE.md           # このファイル
```

## Frontmatter仕様

### profile.md

```yaml
---
nickname: "表示名"                    # 任意
position: "ポジション"               # 任意
career_started_year: 2018            # 任意、YYYY形式
availability: fulltime               # 任意: fulltime | partial | sidejob | not_available
desired_hourly_rate: 5000            # 任意、正の整数
available_hours_per_week: 40         # 任意、0-168
x_account_url: "https://x.com/xxx"  # 任意、URL形式
education: "東京大学工学部卒業"      # 任意、学歴（自由記述）
desired_annual_income: 800           # 任意、希望年収（万円単位）
preferred_locations: "東京, リモート" # 任意、希望勤務地
birth_year: 1995                     # 任意、生年（1940-2010）
profile_image_url: "https://..."     # 任意、プロフィール画像URL
---

本文はキャリアサマリーとして表示されます。
```

### skills.yml

```yaml
languages:
  - name: "TypeScript"
    experience: "over_3_years"   # 任意: half_year | 1_year | 2_years | 3_years | over_3_years
frameworks:
  - name: "React"
services:
  - name: "AWS"
```

### projects/*.md

```yaml
---
title: "プロジェクト名"        # 必須
company: "会社名"             # 必須
status: published             # 任意: draft | published（デフォルト: published）
started: "2024-04"            # 任意、YYYY-MM形式
ended: "2024-12"              # 任意、YYYY-MM形式（進行中は省略）
duration: "6ヶ月"             # 任意、自由テキスト
skills: ["Go", "AWS"]        # 任意
tags: ["Backend"]             # 任意
role: "テックリード"           # 任意
team_size: 5                  # 任意、正の整数
order: 1                     # 任意、表示順
---

本文はMarkdownで自由に記述。プロジェクトの説明として表示されます。
```

### histories/*.md

```yaml
---
company: "会社名"              # 必須
type: employee                # 必須: employee | freelance | sidejob
position: "ポジション"        # 必須
from: "2020-04"               # 必須、YYYY-MM形式
to: "2024-03"                 # 任意、YYYY-MM形式（在職中は省略）
summary: "概要（120文字以内）" # 任意
skills: ["Go", "AWS"]        # 任意
order: 1                     # 任意、表示順
---

本文はMarkdownで自由に記述。詳細な業務内容として使用できます。
```

## 操作方法

1. ファイルを編集してpushするとレジュメが自動更新されます
2. `status: draft` にすると公開レジュメに表示されません
3. ファイルを削除すると対応するデータも削除されます

## Claude Codeでの編集

Claude Codeを使ってこのリポジトリの内容を編集できます：

- 「新しいプロジェクトを追加して」→ projects/ にMarkdownファイルを作成
- 「経歴を更新して」→ histories/ のファイルを編集
- 「スキルにDockerを追加して」→ skills.yml を編集
- 「プロフィールを書き直して」→ profile.md を編集
