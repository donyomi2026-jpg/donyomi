# ドンヨミ 公開版（静的サイト）

このフォルダの中身をそのまま静的ホスティングに置けば動きます（ビルド不要・サーバー処理なし）。

## GitHub Pages で公開する
1. 新しいリポジトリを作り、このフォルダの中身（`.nojekyll` を含む）をリポジトリ直下に push。
2. Settings → Pages → Source を「Deploy from a branch」、Branch を `main` / `/(root)` にして保存。
3. 数分後に `https://<ユーザー名>.github.io/<リポジトリ名>/` で公開されます。

## 公開URLが決まったらやること
- `index.html` の `og:image` と `twitter:image` を `og.png` の絶対URL（例 `https://<ユーザー名>.github.io/<リポジトリ名>/og.png`）に書き換える。X のカードは相対パスだと画像が出ません。
- 必要なら `og:url` と `<link rel="canonical">` も追加。

## ファイル
- `index.html` … 本体（店舗データ・SVG・CSS・JSをすべて内蔵）。`/home/claude/site/build_public.py` で `src.html` から生成。
- `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png`, `favicon.png` … ホーム画面追加用（service worker は未導入）
- `og.png` … シェア用画像（1200×630）
- `404.html`, `.nojekyll`

## Claude版との違い
- 共有の記録（投稿）はまだ保存できません。投稿は Claude版（要ログイン）へ案内しています。
- 「あなたの記録」はこの端末のブラウザ（localStorage）にだけ保存されます。
- コール統計は最初から架空のサンプルデータで表示します。
