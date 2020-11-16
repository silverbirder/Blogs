# Links
TODO

# Title
TODO

# Contents
# What is Micro Frontends ?
皆さん、**Micro Fronends**(以下、MFE)をご存知でしょうか。説明をざっくりすると、Microservicesの考え方をフロントエンドまで拡張した考え方です。Microservicesは、バックエンド側で適用される事例をよく耳にしますが、フロントエンドにはあまり聞いたことがありません。

従来、Webサービス開発では、モノリスな構成からスタートします。そこから、規模が拡大するにつれて結合度を弱くするために、フロントエンドとバックエンドの分離、バックエンドのMicroservices化が行われます。

![monolith-frontback-microservices](https://micro-frontends-japanese.org/resources/monolith-frontback-microservices.png)
※ [[翻訳記事]マイクロフロントエンド](https://micro-frontends-japanese.org/)

Microservices化によって、Scalability、Agility、Independency、Availabilityの大幅な向上が期待できます。

しかし、依然フロントエンドはモノリスなままです。そこで、Microservicesと同様にフロントエンドも縦(専門領域)に分割します。

![verticals-headline](https://micro-frontends-japanese.org/resources/verticals-headline.png)
※ [[翻訳記事]マイクロフロントエンド](https://micro-frontends-japanese.org/)

ただし、全てのフロントエンドをMFEにする必要はありません。

![mfe-web-document-to-web-app](https://media-exp1.licdn.com/dms/image/C5612AQEMjY51MwQMww/article-inline_image-shrink_1000_1488/0?e=1611187200&v=beta&t=EGumrK4ul8MRLTYa-gGjT93c4b7qSFWyzH9mwp5mq0w)
※ [Microfrontends: An approach to building Scalable Web Apps](https://www.linkedin.com/pulse/microfrontends-approach-building-scalable-web-apps-vinci-rufus)

先程の説明にもあったとおり、規模が拡大した際にMFEを検討する必要があるため、小・中規模のWebサービスでは時期尚早です。また、上部の画像にもある通り、静的ページ(Webサイト,Webドキュメント)や動的ページ(Webアプリ)の両極端に位置するWebサービスはMFEの適用するのには不向きです。両方の要素が求められるWebサービスにMFEが役立ちます。MFEの適用事例でよく見るのは、ECサイトが挙げられます。

※ MFEという言葉は、[Micro frontends | Technology Radar | ThoughtWorks](https://www.thoughtworks.com/radar/techniques/micro-frontends) の記事より生まれたみたいです。

※ [Micro Frontends in Action](https://www.manning.com/books/micro-frontends-in-action)にも記載されいますが、この考え方はWebサービスを対象としており、ネイティブアプリは対象としていません。

# Adopted Company
実績企業としては、Facebook、DAZN、Spotifyなどが挙げられます。詳しくは、[Micro Frontends を調べたすべて](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727) にリストアップしています。

# Background of Micro Frontends


# Pros/Cons
## Pros
## Cons

# Integration Pattern
## Build Pattern
## Client Pattern
## Server Pattern

# Conclusion

# Links

* [Micro Frontends を学んだすべて](https://silverbirder180.hatenablog.com/entry/2020/05/04/182921)
* [Ara-Framework で Micro Frontends with SSR](https://silverbirder180.hatenablog.com/entry/2020/08/23/183713)
* [Zalando tailor で Micro Frontends with ( LitElement & etcetera)](https://silverbirder180.hatenablog.com/entry/2020/10/04/095230)
* [Micro Frontends を調べたすべて](https://silverbirder180.hatenablog.com/entry/2020/10/07/190727)
* [Cloudflare Workers (Edge Workers) で Micro Frontends](https://silverbirder180.hatenablog.com/entry/2020/11/15/121730)
