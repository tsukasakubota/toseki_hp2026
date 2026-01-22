# Team AI Template

Claude Code を使ったチーム開発テンプレートです。

## 概要

PM（プロジェクトマネージャー）と各担当（フロント/バック/インフラ）が分業して開発を進めるための構成です。

```
司（人間）
    ↓
   PM（技術判断も担当）
    ↓
┌───┴───┬───────┐
フロント  バック  インフラ
```

## クイックスタート

```bash
# 1. このテンプレートからリポジトリを作成（GitHub: Use this template）
# 2. クローン
git clone https://github.com/[your-name]/[your-project].git
cd [your-project]

# 3. Claude Code で開く
# 4. PMとして開始
/PM
```

## コマンド

| コマンド | 用途 |
|----------|------|
| `/PM` | PM として進捗確認・報告・sharebox管理 |
| `/PM git` | 上記 + ローカルcommit |
| `/PM push` | 上記 + GitHub push |
| `/GO front` | フロントエンド担当として起動 |
| `/GO back` | バックエンド担当として起動 |
| `/GO infra` | インフラ担当として起動 |
| `/restart [担当]` | チャットクリア後の再起動（sharebox読み込み） |

## ディレクトリ構成

```
.
├── .claude/commands/    # Claude Code コマンド定義
│   ├── go.md
│   ├── pm.md
│   └── restart.md
├── pm/                  # PM のタスク管理
│   ├── inbox/          # 未処理の報告
│   └── archive/        # 処理済み
├── front/               # フロントエンド担当
│   ├── inbox/
│   └── archive/
├── back/                # バックエンド担当
│   ├── inbox/
│   └── archive/
├── infra/               # インフラ担当
│   ├── inbox/
│   └── archive/
├── sharebox/            # 全体の指示・報告記録
├── docs/                # ドキュメント
└── src/
    ├── frontend/        # フロントエンドコード
    └── backend/         # バックエンドコード
```

## ワークフロー

### 1. タスク発行

PMが各担当の `inbox/` にタスクファイルを作成

### 2. タスク実行

各担当が `/GO [担当名]` で起動し、`inbox/` のタスクを実行

### 3. 報告

完了したら `archive/` に移動し、`/pm/inbox/` に報告ファイルを作成

### 4. 整理

PMが報告を処理し、`sharebox/` に記録

## チャットが長くなったら

```bash
/clear              # チャットをクリア
/restart [担当]     # shareboxから経緯を復元して再開
```

## 技術スタック（デフォルト）

- **フロントエンド**: Next.js, TypeScript, Tailwind CSS
- **バックエンド**: Python, FastAPI, SQLAlchemy, PostgreSQL
- **インフラ**: Vercel, Railway

※ プロジェクトに応じて `go.md` 内の技術スタックを変更してください

## ライセンス

MIT
