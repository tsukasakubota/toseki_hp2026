# /restart コマンド - コンテキスト復元して再起動

チャットをクリアした後、shareboxからプロジェクト経緯を復元して作業を再開します。

## 使い方

```
/clear                 ← チャットをクリア
/restart [担当名]      ← sharebox読み込み + inbox確認
```

例: `/restart front`, `/restart back`, `/restart infra`, `/restart pm`

## 引数: $ARGUMENTS

---

## 実行手順

### 1. shareboxを読み込む

`/sharebox/` 内のファイルを**全て読んで**、プロジェクトの経緯を把握する。

確認すべき内容:
- これまでにどんな指示が出されたか
- 各担当が何を完了したか
- 現在のプロジェクト状況

### 2. 自分の役割を確認

引数に応じて担当を設定:

| 引数 | 役割 |
|------|------|
| `front` | フロントエンド担当 |
| `back` | バックエンド担当 |
| `infra` | インフラ担当 |
| `pm` | PM |

### 3. inboxを確認

自分の `inbox/` を確認し、未処理のタスクがあれば作業開始。

| 担当 | inbox |
|------|-------|
| front | `/front/inbox/` |
| back | `/back/inbox/` |
| infra | `/infra/inbox/` |
| pm | `/pm/inbox/` |

### 4. 司に状況報告

```
shareboxから経緯を復元しました。

## 把握した状況
- [これまでの経緯サマリー]

## 現在のinbox
- [未処理タスクがあれば記載]

## 次のアクション
- [何をするか]
```

---

## 担当別の詳細

### `/restart front`

フロントエンド担当として再起動。

- sharebox読み込み → 全体把握
- `/front/inbox/` 確認
- 技術スタック: Next.js, TypeScript, Tailwind CSS
- コード担当: `src/frontend/`
- 報告先: `/pm/inbox/`

### `/restart back`

バックエンド担当として再起動。

- sharebox読み込み → 全体把握
- `/back/inbox/` 確認
- 技術スタック: Python, FastAPI, SQLAlchemy, PostgreSQL
- コード担当: `src/backend/`
- 報告先: `/pm/inbox/`

### `/restart infra`

インフラ担当として再起動。

- sharebox読み込み → 全体把握
- `/infra/inbox/` 確認
- 担当範囲: Railway, Vercel, GitHub Actions
- 報告先: `/pm/inbox/`

### `/restart pm`

PMとして再起動。

- sharebox読み込み → 全体把握
- `/pm/inbox/` 確認
- 全体の進捗状況を司に報告

---

## 通常の /GO との違い

| コマンド | 動作 |
|----------|------|
| `/GO [担当]` | inboxだけ確認して作業開始 |
| `/restart [担当]` | **shareboxを先に読んで**からinbox確認 |

`/restart` はチャットクリア後の「記憶の復元」に使います。

---

## 注意事項

- `/restart` はチャットをクリアした後に使用してください
- shareboxの読み込みには時間がかかる場合があります
- 復元後は通常通り作業を進めてください
