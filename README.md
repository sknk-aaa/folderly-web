# folderly-web

Folderly の紹介/マーケティングサイト。Cloudflare Pages で `folderlyapp.com` に公開する静的サイト。
（アプリ本体のリポジトリは別: `folderly-win`）

## 構成
- `/`            英語 LP（x-default）
- `/ja/`         日本語 LP
- `/privacy/`    プライバシーポリシー＋FAQ＋サポート（日英1ページ）
- `/blog/`       how-to 記事（予定）
- `sitemap.xml`, `robots.txt`
- `/assets/`     スクリーンショット等の画像（予定）

## SEO
- 各ページに hreflang（en / ja / x-default）。canonical は apex（`folderlyapp.com`）。
- title ≤ 60字 / description ≈ 120字 / H1 は1つ。

## デプロイ（Cloudflare Pages）
- Workers & Pages → Pages → このリポジトリを接続。
- Build command: なし（静的）/ Output directory: `/`（ルート）。
- Custom domain: `folderlyapp.com`（apex）、`www` は apex へ 301 リダイレクト。
- Cloudflare Web Analytics を有効化（無料・Cookie同意不要）。

## メモ
- `/index.html`・`/ja/index.html` は ChatGPT モックの HTML を差し込む前提のプレースホルダ。
- マーケ戦略・狙いキーワード・LP構成は app リポの `docs/MARKETING.md` を参照。
