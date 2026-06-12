<!-- プロジェクトのディレクトリ構成と各フォルダの役割を記載 -->

# ディレクトリ構成

```
Portfolio_Site/
├── frontend/                   # Astro × React フロントエンド
│   ├── public/                 # 静的ファイル (favicon, OGP画像など)
│   ├── src/
│   │   ├── components/         # 再利用可能なコンポーネント
│   │   │   ├── ui/             # 汎用UIパーツ (Button, Card等)
│   │   │   └── sections/       # ページセクション (Hero, Works等)
│   │   ├── content/            # Markdownコンテンツ
│   │   │   ├── works/          # 成果物カード (.md)
│   │   │   └── news/           # 最近のニュース (.md)
│   │   ├── layouts/            # ページレイアウト
│   │   ├── pages/              # ルーティング (index.astro等)
│   │   └── styles/             # グローバルCSS
│   ├── astro.config.mjs        # Astro設定
│   ├── tsconfig.json           # TypeScript設定
│   └── package.json
│
├── backend/                    # Go REST API
│   ├── cmd/
│   │   └── server/             # エントリーポイント (main.go)
│   ├── internal/
│   │   ├── handler/            # HTTPハンドラー
│   │   └── github/             # GitHub APIクライアント
│   ├── go.mod
│   └── go.sum
│
├── docs/                       # プロジェクトドキュメント
│   ├── 0_setup_owner.md        # オーナー向けセットアップ
│   ├── 1_setup_devbox.md       # Devbox環境セットアップ
│   ├── 2_setup.md              # 依存インストール・サーバー起動
│   ├── architecture.md         # アーキテクチャ設計
│   ├── coding_rules.md         # コーディング規約
│   ├── commands.md             # よく使うコマンド集
│   ├── design.md               # プロダクト設計
│   ├── directory_structure.md  # このファイル
│   ├── env_variables.md        # 環境変数管理
│   ├── git_workflow.md         # Git運用ルール
│   ├── github_labels.md        # GitHubラベル定義
│   └── setup_error_handling.md # セットアップエラー対処法
│
├── devbox.json                 # Devbox パッケージ・スクリプト定義
├── devbox.lock                 # Devbox ロックファイル
└── .gitignore
```
