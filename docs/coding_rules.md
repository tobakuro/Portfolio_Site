<!-- 命名規則・フォーマッタ・linter設定・言語別のルールを記載 -->

# コーディング規約

---

## 共通

- インデント: スペース2つ
- 文字コード: UTF-8
- 改行コード: LF

---

## TypeScript / Astro

### 型

- `any` は使わず `unknown` を使う
- 型推論できる箇所に明示的な型アノテーションは不要
- コンポーネントのpropsは `interface` で定義する

### 命名規則

| 対象 | 規則 | 例 |
|------|------|----|
| コンポーネントファイル | PascalCase | `WorkCard.astro`, `HeroSection.tsx` |
| 変数・関数 | camelCase | `fetchGithubData` |
| 定数 | UPPER_SNAKE_CASE | `API_BASE_URL` |
| CSSクラス | kebab-case | `work-card__title` |

### Astroコンポーネント

- `.astro` ファイルをデフォルトとし、インタラクティブな箇所のみ `.tsx` を使う
- React コンポーネントに `client:*` ディレクティブをつける際は必要最小限にする

### フォーマット・Lint

- Prettier でフォーマット統一（設定はfrontend/配下）
- ESLint でコード品質チェック
- 型チェックは `devbox run typecheck`

---

## Go

### 命名規則

| 対象 | 規則 | 例 |
|------|------|----|
| パッケージ | 小文字・単数形 | `handler`, `github` |
| 公開関数・型 | PascalCase | `FetchRepos` |
| 非公開関数・変数 | camelCase | `parseResponse` |
| 定数 | PascalCase（公開）/ camelCase（非公開） | `MaxRetry` |

### エラーハンドリング

- エラーは握りつぶさず、必ずラップして意味のあるメッセージを付ける
- `fmt.Errorf("fetchRepos: %w", err)` のようにコンテキストを付与する

### フォーマット・Lint

- `gofmt` / `goimports` でフォーマット
- `go vet` でチェック

---

## コメント

- コードを読めばわかる内容はコメントしない
- 「なぜそう書いたか」（非自明な制約・回避策・意図）のみコメントする
- 英語・日本語どちらでも可
