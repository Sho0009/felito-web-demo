# Felito Corporate Site

合同会社Felitoのコーポレートサイト用リポジトリです。

`index.html` と `assets/css/style.css` を中心に構成された静的サイトで、サービス「BizDev派遣」の紹介、支援内容、実績、会社情報、問い合わせ導線を掲載しています。

## ローカルで確認する方法

このリポジトリはビルド不要です。任意のローカルHTTPサーバーで確認できます。

```sh
cd corporate
python3 -m http.server 5173
```

起動後、ブラウザで以下を開きます。

```txt
http://localhost:5173
```

停止する場合は、サーバーを起動したターミナルで `Ctrl+C` を押してください。

## 本番環境サイトURL

https://felito.co
