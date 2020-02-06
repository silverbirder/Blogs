# Links
TBD

# Title
Algolia + Cloudinary + Google Cloud Vision API on Cloud Run でTiqav2(画像会話用画像検索サービス)を作ってみた
(Typescript + InversifyJS + CleanArchitecture)

# Contents
皆さん、LINEでスタンプって使ってますか？僕はよく使ってます。

人とコミュニケーションをするのに、文字だけだと堅苦しくなりがちです。

『OKです、それで進めてください』
というフレーズだけって、相手の感情が読む取りにくいですよね。

LINEのスタンプ（画像）を送信することで、会話の雰囲気を柔らかくすることができます。
https://res.cloudinary.com/silverbirder/image/upload/v1580997144/LGTM/golia.png

いいかんじですね！

こういった画像を使って会話をするためのサービスTiqavがあります。
http://dev.tiqav.com/

現在は、サービス終了しています。
Tiqav2は、そのTiqavをインスパイヤされて作りました。

# Tiqav2

ざっくり下記の機能です。

1. 画像データの保存
2. 画像の検索
3. 画像の表示

大きな作りとしては、

<図！>

1. 画像のテキストをGoogle Cloud Vision APIで抽出（手動で設定可。quote引数）
2. 画像をcloudinaryに保存し、そのURLを手に入れる (si=1のみ。それ以外は、元のURLが手に入る)
3. 1と2の結果をalgoliaに保存
4. 検索する際は、algoliaに問い合わせ
5. 検索すると、JSON形式でレスポンス
6. idと拡張子を指定することで、画像が返却される

# SaaSの適材適所

# 楽しみましょう！

Good Bye!

よければ、follow@me!
