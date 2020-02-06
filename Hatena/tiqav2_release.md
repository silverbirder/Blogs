# Links
TBD

# Title
Algolia + Cloudinary + Google Cloud Vision API on Cloud Run でTiqav2(画像会話用画像検索サービス)を作ってみた
(Typescript + InversifyJS + CleanArchitecture)

[:contents]

# 画像で会話って楽しい
皆さん、LINEでスタンプって使ってますか？僕はよく使ってます。
人とコミュニケーションするのに、文字だけだと<b>堅苦しくなりがち</b>です。

『OKです、それで進めてください』というフレーズだけって、相手の感情が読む取りにくいですよね。怒なの？


LINEのスタンプ（画像）を送信することで、会話の雰囲気を柔らかくすることができます。
例えば、こういう画像です。
[https://res.cloudinary.com/silverbirder/image/upload/v1580997144/LGTM/golia.png:image=https://res.cloudinary.com/silverbirder/image/upload/v1580997144/LGTM/golia.png]

こういった画像を使って会話をするためのサービスTiqavがあります。
[http://dev.tiqav.com/:embed:cite]

現在は、サービス終了しています。
Tiqav2は、そのTiqavをインスパイヤされて作りました。

# Tiqav2について

Tiqav2は、

画像を

1. 保存
1. 検索
1. 表示

という３機能があります。

まず、画像を保存する機能は、次のような図です。
<figure class="figure-image figure-image-fotolife" title="Searching Flow  By Tiqav2">[f:id:silverbirder180:20200207074252p:plain]<figcaption>Searching Flow  By Tiqav2</figcaption></figure>


次に、検索と表示する機能は、次のような図です。
<figure class="figure-image figure-image-fotolife" title="Searching Flow  By Tiqav2">[f:id:silverbirder180:20200207074256p:plain]<figcaption>Searching Flow  By Tiqav2</figcaption></figure>

# SaaSの適材適所

# 楽しみましょう！

Good Bye!

よければ、follow@me!