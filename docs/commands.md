<!-- 開発でよく使うコマンドをまとめて記載 -->

# よく使うコマンド集

すべてのコマンドは `devbox shell` 内で実行してください。

---

## セットアップ

```bash
devbox run setup          # frontend の依存パッケージインストール (pnpm install)
```

---

## 開発サーバー

```bash
devbox run dev:front      # Astro開発サーバー起動 → http://localhost:4321
devbox run dev:back       # Go APIサーバー起動 → http://localhost:8080
```

---

## ビルド

```bash
devbox run build          # Astro 本番ビルド (frontend/dist/ に出力)
```

---

## テスト

```bash
devbox run test:front     # フロントエンドテスト
devbox run test:back      # Go テスト (go test ./...)
```

---

## 品質チェック

```bash
devbox run lint           # ESLint
devbox run typecheck      # astro check (TypeScript型チェック)
```

---

## Go (backend/ で直接実行する場合)

```bash
go test ./...             # テスト
go vet ./...              # 静的解析
go build ./...            # ビルド
go mod tidy               # go.mod / go.sum の整理
```

---

## pnpm (frontend/ で直接実行する場合)

```bash
pnpm install              # 依存インストール
pnpm dev                  # 開発サーバー起動
pnpm build                # ビルド
pnpm astro check          # 型チェック
pnpm astro add <name>     # インテグレーション追加
```

---

## git

```bash
git switch -c feat/<issue番号>/<説明>   # フィーチャーブランチ作成
git add <file>                          # ステージング
git commit -m "feat: 〇〇を追加"        # コミット (Conventional Commits形式)
git push -u origin <branch>            # プッシュ
```
