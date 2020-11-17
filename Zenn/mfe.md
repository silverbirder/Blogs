# Links
TODO

# Title
[覚書] Micro Frontends 📚

# Contents
# Micro Frontends とは?🤔
皆さん、**Micro Fronends**(以下、MFE)をご存知でしょうか。説明をざっくりしますと、Microservicesの考え方をフロントエンドまで拡張した考え方です。Microservicesは、バックエンド側で適用される事例をよく耳にしますが、フロントエンドでの適用事例は、あまり聞いたことがありません。

従来、Webサービス開発ではモノリスな構成からスタートします。そこから、規模が拡大するにつれて様々な理由により、フロントエンドとバックエンドの分離、バックエンドのMicroservices化が行われます。

![monolith-frontback-microservices](https://micro-frontends-japanese.org/resources/monolith-frontback-microservices.png)
*[[翻訳記事]マイクロフロントエンド](https://micro-frontends-japanese.org/)*

Microservices化によって、Scalability、Agility、Independency、Availabilityの大幅な向上が期待できます。しかし、依然フロントエンドはモノリスなままです。

![verticals-headline](https://micro-frontends-japanese.org/resources/verticals-headline.png)
*[[翻訳記事]マイクロフロントエンド](https://micro-frontends-japanese.org/)*

そこで、Microservicesと同様にフロントエンドも縦(専門領域)に分割します。

![mfe-web-document-to-web-app](https://media-exp1.licdn.com/dms/image/C5612AQEMjY51MwQMww/article-inline_image-shrink_1000_1488/0?e=1611187200&v=beta&t=EGumrK4ul8MRLTYa-gGjT93c4b7qSFWyzH9mwp5mq0w)
*[Microfrontends: An approach to building Scalable Web Apps](https://www.linkedin.com/pulse/microfrontends-approach-building-scalable-web-apps-vinci-rufus)*

ただし、全てのフロントエンドをMFEにする必要はありません。先程の説明にもあった通り、規模が拡大した際にMFEを検討する必要があるため、小・中規模のWebサービスでは時期尚早です。また、上部の画像にもある通り、静的ページ(Webサイト,Webドキュメント)や動的ページ(Webアプリ)の両極端に位置するWebサービスはMFEの適用するのには不向きです(と書いています)。両方の要素が求められるWebサービスにMFEが役立ちます。MFEの適用されるWebサービス事例では、ECサイトが挙げられます。

※ MFEという言葉は、[Micro frontends | Technology Radar | ThoughtWorks](https://www.thoughtworks.com/radar/techniques/micro-frontends) の記事より生まれたみたいです。
※ [Micro Frontends in Action](https://www.manning.com/books/micro-frontends-in-action)にも記載されていますが、この考え方はWebサービスを対象としており、ネイティブアプリは対象としていません。

# 導入企業👨‍💼👩‍💼
実績企業としては、IKEA、DAZN、Spotifyなどが挙げられます。他の例は、[Micro Frontends を調べたすべて](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727) にリストアップしていますので、興味がある方はご覧ください。

# メリット・デメリット🔍
MFEを導入することによるメリット・デメリットについて、(プロダクション導入経験無しの私が偏見で)簡単に紹介します。
私が思う最大のメリットは、**Agility**と思います。規模が中・大規模なWebサービスとなると、様々な業務ドメインが詰め込まれます。先程のMFEの例(ECサイト)でいうと、推薦(inspire)、検索(search)、商品(product)、注文(checkout)などにあたります。これらを1つのフロントエンドで構築すると、ドメイン設計を適切に分離できたとしても、**開発者の業務ドメイン知識が追いつかず、開発スピードが低下してしまいます**。結果、特定の開発者の属人化が加速し、ボトルネックとなります。
そこで、それぞれ**業務ドメインを分割することで、開発者はそこだけにフォーカスできます。結果、開発スピードは維持できるはずです**。

私が思う最大のデメリットは、**Independencyの難しさ**だと思います。例えば、UI/UXの指針となるデザインシステムがWebサービスにあったとして、それをすべてのフロントエンドへ適用しなければならないです。また、全体を通した**一貫性のあるUI/UXであるかどうか**の品質担保も必要です。
他には、あるチームのビルドツールを改善したとしても、他のチームではその恩恵を受けれなかったり、アプリケーション設計における全体共通(アクセス履歴、イベント管理、状態管理など)部分を、どうするか考える必要があります。

こちら [Micro Frontends を調べたすべて#ProsCons](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727#ProsCons) にも簡単にメリット・デメリットを書いていますので、気になる方はご覧ください。

# 統合パターン🔮
## ビルド 統合パターン

![build integration pattern](https://bluesoft.com/wp-content/uploads/2020/04/Micro-Frontends-9.jpg)
*[Micro Frontends – The Missing Piece Of The Puzzle In Feature Teams | BlueSoft](https://bluesoft.com/micro-frontends-the-missing-piece-of-the-puzzle-in-feature-teams/)*

ちょっと図がわかりにくいかもですね。有名所では、bit.devです。

![bit.dev toppage](https://storage.googleapis.com/zenn-user-upload/e74w0sjnj1r0zpzvd5xfvsk7k1bd)
*[bit.dev](https://bit.dev/)*

## クライアントサイド 統合パターン

![client side integration pattern](https://bluesoft.com/wp-content/uploads/2020/04/Micro-Frontends-10.jpg)
*[Micro Frontends – The Missing Piece Of The Puzzle In Feature Teams | BlueSoft](https://bluesoft.com/micro-frontends-the-missing-piece-of-the-puzzle-in-feature-teams/)*

iframeやwebcomponent ですね。

## サーバーサイド 統合パターン

![server side integration pattern](https://bluesoft.com/wp-content/uploads/2020/04/Micro-Frontends-11.jpg)
*[Micro Frontends – The Missing Piece Of The Puzzle In Feature Teams | BlueSoft](https://bluesoft.com/micro-frontends-the-missing-piece-of-the-puzzle-in-feature-teams/)*

podiumやtailorなどですね。

サーバーサイドのサンプルコードは、次にまとめています。

* [Micro Frontends を学んだすべて](https://silverbirder180.hatenablog.com/entry/2020/05/04/182921)
* [Ara-Framework で Micro Frontends with SSR](https://silverbirder180.hatenablog.com/entry/2020/08/23/183713)
* [Zalando tailor で Micro Frontends with ( LitElement & etcetera)](https://silverbirder180.hatenablog.com/entry/2020/10/04/095230)
* [Cloudflare Workers (Edge Workers) で Micro Frontends](https://silverbirder180.hatenablog.com/entry/2020/11/15/121730)

# 結論👨‍💻👩‍💻
まだまだ考えなければいけないことがあります。

# 関連リンク🔗
私が書いたMFE関連の記事です。もしよければご覧ください。

* [Micro Frontends を学んだすべて](https://silverbirder180.hatenablog.com/entry/2020/05/04/182921)
* [Micro Frontends を調べたすべて](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727)
* [Ara-Framework で Micro Frontends with SSR](https://silverbirder180.hatenablog.com/entry/2020/08/23/183713)
* [Zalando tailor で Micro Frontends with ( LitElement & etcetera)](https://silverbirder180.hatenablog.com/entry/2020/10/04/095230)
* [Cloudflare Workers (Edge Workers) で Micro Frontends](https://silverbirder180.hatenablog.com/entry/2020/11/15/121730)
