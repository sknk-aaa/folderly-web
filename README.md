# folderly-web

Folderly の紹介/マーケティングサイト。Cloudflare Pages で `folderlyapp.com` に公開する静的サイト。
（アプリ本体のリポジトリは別: `folderly-win`）

## 構成
- `/`            日本語 LP（x-default。主市場が日本のためルートに配置）
- `/en/`         英語 LP（予定）
- `/privacy/`    プライバシーポリシー＋FAQ＋サポート（日英1ページ）
- `/blog/`       how-to 記事（予定）
- `sitemap.xml`, `robots.txt`
- `/assets/`     LP用スクリーンショット・ロゴ画像

## SEO
- hreflang（ja / x-default = `/`）。`/en/` 作成時に `en` を追加。canonical は apex（`folderlyapp.com`）。
- LP本体は Claude Design ハンドオフ（`Folderly LP.html`）を忠実再現したもの。価格は ¥500 買い切り。

## デプロイ（Cloudflare Pages）
- Workers & Pages → Pages → このリポジトリを接続。
- Build command: なし（静的）/ Output directory: `/`（ルート）。
- Custom domain: `folderlyapp.com`（apex）、`www` は apex へ 301 リダイレクト。
- Cloudflare Web Analytics を有効化（無料・Cookie同意不要）。

## メモ
- 画像は `/assets/`（app-icon・showcase-explorer/customize/tags/manage・solution-folders）。合計~9MBのため将来WebP化/リサイズ推奨。
- マーケ戦略・狙いキーワード・LP構成は app リポの `docs/MARKETING.md` を参照。
