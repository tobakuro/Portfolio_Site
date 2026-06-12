<!-- Devbox shellに入った後のフロント/バックエンドのサーバー起動手順を記載 -->

# 2. プロジェクトセットアップ手順

このドキュメントでは、`devbox shell` に入った後の依存関係のインストールとサーバー起動手順を記載します。

> Devbox環境のセットアップがまだの場合は [`1_setup_devbox.md`](./1_setup_devbox.md) を先に参照してください。

---

## 全体の流れ

```
STEP 1. devbox shell に入る
STEP 2. 依存パッケージのインストール
STEP 3. 開発サーバーの起動
```

---

## STEP 1. devbox shell に入る

```bash
cd ~/github/Portfolio_Site
devbox shell
```

---

## STEP 2. 依存パッケージのインストール

```bash
devbox run setup
```

内部で `cd frontend && pnpm install` が実行されます。

---

## STEP 3. 開発サーバーの起動

### フロントエンド (Astro)

```bash
devbox run dev:front
```

`http://localhost:4321` でアクセスできます。

### バックエンド (Go)

```bash
devbox run dev:back
```

`http://localhost:8080` でアクセスできます（ポートはbackend実装時に確定）。

---

## devbox スクリプト一覧

| コマンド | 内容 |
|---|---|
| `devbox run setup` | frontendの依存パッケージインストール |
| `devbox run dev:front` | Astro開発サーバー起動 |
| `devbox run dev:back` | Go APIサーバー起動 |
| `devbox run build` | Astroの本番ビルド |
| `devbox run test:front` | フロントエンドテスト実行 |
| `devbox run test:back` | バックエンドテスト実行 |
| `devbox run lint` | ESLintによるlintチェック |
| `devbox run typecheck` | Astro型チェック |
