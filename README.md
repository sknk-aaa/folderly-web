# folderly-web

## 2026-08-20 Update

### 今回反映したこと

- 日本語/英語LPのファーストビューに、写真カバー・色タグ・ローカル処理・履歴復元の訴求を追加。
- LP内に用途別の見せ方（仕事、写真、制作、学習）を追加し、購入前に自分の使い道を想像しやすくした。
- `/blog/folder-icon-not-changing/` に症状別の導線と、ネットワークフォルダ/NAS/共有フォルダの注意を追加。
- `/blog/folderly-how-to/` にネットワークフォルダの注意と日本語問い合わせフォームへの導線を追加。
- `/en/blog/folderly-how-to/` を新規作成し、英語ブログ一覧と `sitemap.xml` に追加。
- `/privacy/` のサポート導線を Tally フォーム（日英）に統一。

### 公開後に見るURL

| URL | 見る理由 |
|---|---|
| `https://folderlyapp.com/` | 日本語LP。ファーストビューの訴求、用途別ブロック、価格/Store CTAが自然に見えるか確認する。 |
| `https://folderlyapp.com/en/` | 英語LP。海外向けに写真カバー・色タグ・ローカル処理の価値が伝わるか確認する。 |
| `https://folderlyapp.com/blog/folder-icon-not-changing/` | GSC流入が多い困りごと記事。症状別カードとネットワークフォルダの注意が強すぎないか確認する。 |
| `https://folderlyapp.com/blog/folderly-how-to/` | 日本語の使い方記事。購入前の不安解消とサポート導線を確認する。 |
| `https://folderlyapp.com/en/blog/folderly-how-to/` | 新規英語記事。海外向けの使い方説明として不自然な表現がないか確認する。 |
| `https://folderlyapp.com/en/blog/` | 英語ブログ一覧。新規記事が先頭に出ているか確認する。 |
| `https://folderlyapp.com/privacy/#support` | Tallyの日英問い合わせフォーム導線が正しいか確認する。 |

## 2026-07-30 Update

### 今日反映したこと

- 日本語LPのH1を「フォルダアイコンを、好きな画像に変更。」へ変更。
- 訴求を「フォルダを写真と色タグで見分けやすく」に統一。
- 日本語/英語LPに「Windows標準 vs Folderly」の比較ブロックを追加。
- FAQに無料試用、安全性、日本語対応、色タグだけ利用の説明を追加。
- `/blog/windows-folder-icon-change/` を「フォルダアイコン 変更方法」寄りの本命SEO記事として更新。
- `/blog/folder-icon-not-changing/` に症状別CTAを追加。
- `/blog/folderly-how-to/` を新規作成。
- `blog/index.html` と `sitemap.xml` に新規記事を追加。

### 公開後に見るURL

| URL | 見る理由 |
|---|---|
| `https://folderlyapp.com/` | 日本語LP。ファーストビュー、比較ブロック、FAQ、CTAが購入につながるか確認する。 |
| `https://folderlyapp.com/en/` | 英語LP。海外向けに `photos + color tags` と `no .ico conversion` が自然に伝わるか確認する。 |
| `https://folderlyapp.com/blog/windows-folder-icon-change/` | 本命SEO記事。検索意図に答えてから自然にFolderlyへ送客できているか確認する。 |
| `https://folderlyapp.com/blog/folder-icon-not-changing/` | 困りごと記事。症状別CTAが押しつけに見えないか確認する。 |
| `https://folderlyapp.com/blog/folderly-how-to/` | 新規使い方記事。購入前の不安解消になっているか確認する。 |
| `https://folderlyapp.com/blog/` | 新規記事と更新記事が一覧に出ているか確認する。 |

### 公開後の作業

1. Cloudflare Pagesのデプロイ完了を確認する。
2. Search Consoleで更新URLと新規URLのインデックス登録をリクエストする。
3. 2-4週間後にGSCで表示回数/CTR/クエリを見て、記事タイトルと本文を微調整する。

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
- LP本体は Claude Design ハンドオフ（`Folderly LP.html`）を忠実再現したもの。通常価格は ¥480 / $2.99 買い切り。2026-09-02 までは改善版リリース記念価格として日本 ¥300、海外 $1.49 をLP上で訴求。

## デプロイ（Cloudflare Pages）
- Workers & Pages → Pages → このリポジトリを接続。
- Build command: なし（静的）/ Output directory: `/`（ルート）。
- Custom domain: `folderlyapp.com`（apex）、`www` は apex へ 301 リダイレクト。
- Cloudflare Web Analytics を有効化（無料・Cookie同意不要）。

## メモ
- 画像は `/assets/`（app-icon・showcase-explorer/customize/tags/manage・solution-folders）。合計~9MBのため将来WebP化/リサイズ推奨。
- マーケ戦略・狙いキーワード・LP構成は app リポの `docs/MARKETING.md` を参照。
