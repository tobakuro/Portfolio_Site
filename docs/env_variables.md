<!-- 環境変数の管理ルール・必要キー一覧・取得方法を記載 -->

# 環境変数管理

---

## 管理ルール

- 環境変数は `.env` ファイルで管理する（gitignore済み）
- `.env.example` にキー名と説明のみを記載し、値は書かない
- 本番環境の値は各クラウドサービスのダッシュボードで設定する

---

## フロントエンド (`frontend/.env`)

Astroでは `PUBLIC_` プレフィックスをつけた変数のみブラウザに公開される。

| 変数名 | 必須 | 説明 |
|--------|------|------|
| `PUBLIC_API_BASE_URL` | ○ | Go APIサーバーのベースURL (例: `http://localhost:8080`) |

---

## バックエンド (`backend/.env`)

| 変数名 | 必須 | 説明 | 取得方法 |
|--------|------|------|---------|
| `GITHUB_TOKEN` | ○ | GitHub APIトークン | GitHub Settings → Developer settings → Personal access tokens |
| `PORT` | - | サーバーのポート番号（デフォルト: `8080`） | - |
| `ALLOWED_ORIGIN` | ○ | CORSで許可するオリジン（本番: Cloudflare PagesのURL） | - |

---

## 本番環境での設定

### Cloudflare Pages (フロントエンド)

Settings → Environment variables で `PUBLIC_API_BASE_URL` を設定。

### Fly.io (バックエンド)

```bash
fly secrets set GITHUB_TOKEN=<your-token>
fly secrets set ALLOWED_ORIGIN=https://<your-pages-url>
```
