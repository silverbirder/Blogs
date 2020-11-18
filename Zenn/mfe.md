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

Microservices化によって、Scalability、Agility、Independency、Availabilityの大幅な向上が期待できます。しかし、依然フロントエンドはモノリスなままです。そこで、次の画像のように、Microservicesと同様にフロントエンドも縦(専門領域)に分割します。

![verticals-headline](https://micro-frontends-japanese.org/resources/verticals-headline.png)
*[[翻訳記事]マイクロフロントエンド](https://micro-frontends-japanese.org/)*

ただし、全てのフロントエンドをMFEにする必要はありません。先程の説明にもあった通り、規模が拡大した際にMFEを検討する必要があるため、小・中規模のWebサービスでは時期尚早です。また、次の画像にもある通り、静的ページ(Webサイト,Webドキュメント)や動的ページ(Webアプリ)の両極端に位置するWebサービスはMFEの適用するのには不向きです(と書いています)。両方の要素が求められるWebサービスにMFEが役立ちます。MFEの適用されるWebサービス事例では、ECサイトが挙げられます。

![mfe-web-document-to-web-app](https://media-exp1.licdn.com/dms/image/C5612AQEMjY51MwQMww/article-inline_image-shrink_1000_1488/0?e=1611187200&v=beta&t=EGumrK4ul8MRLTYa-gGjT93c4b7qSFWyzH9mwp5mq0w)
*[Microfrontends: An approach to building Scalable Web Apps](https://www.linkedin.com/pulse/microfrontends-approach-building-scalable-web-apps-vinci-rufus)*


※ MFEという言葉は、[Micro frontends | Technology Radar | ThoughtWorks](https://www.thoughtworks.com/radar/techniques/micro-frontends) の記事より生まれたみたいです。
※ [Micro Frontends in Action](https://www.manning.com/books/micro-frontends-in-action)にも記載されていますが、この考え方はWebサービスを対象としており、ネイティブアプリは対象としていません。

# 導入企業👨‍💼👩‍💼
実績企業としては、IKEA、DAZN、Spotifyなどが挙げられます。他の例は、[Micro Frontends を調べたすべて](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727) にリストアップしていますので、興味がある方はご覧ください。

# メリット・デメリット🔍
MFEを導入することによるメリット・デメリットについて、(プロダクション導入経験無しの私が偏見で)簡単に紹介します。
私が思う最大のメリットは、**Agility**と思います。規模が中・大規模なWebサービスとなると、様々な業務ドメインが詰め込まれます。先程のMFEの例(ECサイト)でいうと、推薦(inspire)、検索(search)、商品(product)、注文(checkout)などにあたります。これらを1つのフロントエンドで構築すると、ドメイン設計を適切に分離できたとしても、**開発者の業務ドメイン知識が追いつかず、開発スピードが低下してしまいます**。結果、特定の開発者の属人化が加速し、ボトルネックとなります。
そこで、それぞれ**業務ドメインを分割することで、開発者はそこだけにフォーカスできます。結果、開発スピードは維持できるはずです**。

私が思う最大のデメリットは、**Independencyの難しさ**だと思います。例えば、UI/UXの指針となるデザインシステムがWebサービスにあったとして、それをすべてのフロントエンドへ適用しなければいけません。そのため、全体を通した**一貫性のあるUI/UXであるかどうか**の品質担保が難しいです。
他には、あるチームのビルドツールを改善したとしても、他のチームではその恩恵を受けれなかったり、アプリケーション設計における全体共通(アクセス履歴、イベント管理、状態管理など)部分を、どうするか考える必要があります。

こちら [Micro Frontends を調べたすべて#ProsCons](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727#ProsCons) にも簡単にメリット・デメリットを書いていますので、気になる方はご覧ください。

# 統合パターン🔮
MFEでは、各フロントエンドのフラグメント(HTML)を、どのタイミングで統合するのかが重要です。今回はその統合パターンをざっくり紹介します。
例えば、次のMFEの例で言えば、Team-Product、Team-Checkout、Team-Inspireの3つのフロントエンドフラグメント(HTML)があります。これらをどのタイミングで統合するのかがポイントです。

![mfe-three-teams](https://micro-frontends-japanese.org/resources/three-teams.png)
*[[翻訳記事]マイクロフロントエンド](https://micro-frontends-japanese.org/)*


詳しくは、[Micro Frontends を調べたすべて#統合パターン](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727#%E7%B5%B1%E5%90%88%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3) をご覧ください。

## ビルド時統合パターン
ビルド時統合とは、WebサービスをPublishする前のBuildの段階で統合するパターンです。このパターンは、[bit.dev](https://bit.dev)がよく使われます。

![bit.dev toppage](https://storage.googleapis.com/zenn-user-upload/e74w0sjnj1r0zpzvd5xfvsk7k1bd)
*[bit.dev](https://bit.dev/)*

フラグメント(≒コンポーネント)をPackagingし、Packagingしたライブラリをimportさせてbuild(統合)します。あとは、buildした静的コンテンツをPublishさせるだけになります。

## サーバーサイド統合パターン
サーバーサイド統合とは、Webサーバー側のHTML構築段階で統合するパターン。このパターンは、SSIやESI、Podium、Tailor、Ara-Frameworkなどが使われます。

![ssi](https://www.st-andrews.ac.uk/itsnew/web/images/ssi1.jpg)
*[Server-side includes (SSI)](https://www.st-andrews.ac.uk/itsnew/web/ssi/index.shtml)*

フラグメントを提供するWebサーバーを準備し、それらからフラグメント情報を収集し、全体のページHTMLを構築します。それをSSRとしてユーザーへ提供します。

サーバーサイドのサンプルコードは、次にまとめています。

* [Micro Frontends を学んだすべて](https://silverbirder180.hatenablog.com/entry/2020/05/04/182921)
* [Ara-Framework で Micro Frontends with SSR](https://silverbirder180.hatenablog.com/entry/2020/08/23/183713)
* [Zalando tailor で Micro Frontends with ( LitElement & etcetera)](https://silverbirder180.hatenablog.com/entry/2020/10/04/095230)

また、サーバーサイドというよりEdgeでの統合パターンを下記リンクで紹介しています。

![cloudflare-worker](https://raw.githubusercontent.com/Silver-birder/micro-frontends-sample-code-5/f3c20954e6196cb578cd16caaf5999e07306fb51/overview.svg)
*[github.com/Silver-birder/micro-frontends-sample-code-5](https://github.com/Silver-birder/micro-frontends-sample-code-5)*

* [Cloudflare Workers (Edge Workers) で Micro Frontends](https://silverbirder180.hatenablog.com/entry/2020/11/15/121730)

※ リッチなインタラクションUIを表現したいなら、サーバーサイドとクライアントのHydrationをする必要があります。

## クライアントサイド統合パターン
クライアントサイド統合とは、ブラウザ側レンダリングの段階で統合するパターンです。このパターンは、iframeやWebComponentsなどが使われます。

iframeを使ったページ(フラグメント)埋め込みをさせ、全体のページHTMLを統合させたり、WebComponentsのようにカスタムDOMを定義したHTMLタグでページを構成したりします。

![client side integration pattern](https://bluesoft.com/wp-content/uploads/2020/04/Micro-Frontends-11.jpg)
*[Micro Frontends – The Missing Piece Of The Puzzle In Feature Teams | BlueSoft](https://bluesoft.com/micro-frontends-the-missing-piece-of-the-puzzle-in-feature-teams/)*

# 終わりに👨‍💻👩‍💻
MFEのアプローチを実際に導入した企業は、国内だとまだ比較的少なく、どういった場面で役立つのかあまり明確ではありません。ですが、依然モノリスな中・大規模なWebサービスを運用するならば、特にフロントエンドの進化が激しい界隈の中、サービス提供を維持するのは難しいと思います。

# 関連リンク🔗
私が書いたMFE関連の記事です。もしよければご覧ください。

* [Micro Frontends を学んだすべて](https://silverbirder180.hatenablog.com/entry/2020/05/04/182921)
* [Micro Frontends を調べたすべて](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727)
* [MFE関連資料リンク集](https://github.com/Silver-birder/think-micro-frontends/blob/master/research/docs/read.md)
* [Ara-Framework で Micro Frontends with SSR](https://silverbirder180.hatenablog.com/entry/2020/08/23/183713)
* [Zalando tailor で Micro Frontends with ( LitElement & etcetera)](https://silverbirder180.hatenablog.com/entry/2020/10/04/095230)
* [Cloudflare Workers (Edge Workers) で Micro Frontends](https://silverbirder180.hatenablog.com/entry/2020/11/15/121730)
