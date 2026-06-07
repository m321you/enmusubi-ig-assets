# enmusubi-ig-assets

えんむすび（@enmusubi_gotsu）Instagram投稿画像の配信用 **public** リポジトリ。
GitHub raw 経由で配信し、Meta が画像として取得できる（content-type が image/jpeg になる）ようにする。

## 置き方

- 画像は `images/YYYY/MM/` の日付階層に置く（例: `images/2026/06/20260608_ab12cd34ef.jpg`）
- ファイル名は必ずユニーク（日付＋UUID）。**同名で上書きしない**（GitHub raw のキャッシュで古い画像が返る事故を防ぐため）
- 投入は基本 `enmusubi-ig` リポジトリの `publish_image.py` から自動で行う

## 配信URLの形式

```
https://raw.githubusercontent.com/m321you/enmusubi-ig-assets/main/images/YYYY/MM/{filename}.jpg
```

## 置いてはいけないもの

- `.env`・アクセストークン・APP_SECRET などの機密情報は**絶対に置かない**。ここは画像だけ
- コード（投稿ロジック）は置かない。コードは private リポジトリ `enmusubi-ig` 側
