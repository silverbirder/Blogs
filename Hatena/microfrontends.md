# Links
TODO

# Title
Micro Frontends について学んだ すべて

# Content
[f:id:silverbirder180:20200430212240p:plain]

Micro FrontendsというWebフロントエンドアーキテクチャがあります。
このアーキテクチャを知るために、書籍を読み、簡単なサンプルWebアプリを開発しました。
そこから学んだメリット・デメリットを議事録として残したいと思います。

[:contents]

# モノリシックな Webアプリケーション
マイクロサービスという考え方の多くは、バックエンドへ適用されることが一般的です。
一方で、フロントエンドは依然モノリシックなままの状態です。

ECサイトのようなWebアプリケーションでは、様々な専門知識(商品、注文、検索など)を必要とし、フロントエンド開発者の守備範囲がとても広くなってしまいます。
開発者には限界があり、いつしかトラブルシューティングに追われる日々になってしまいます。

そこで、Micro Frontendsというアーキテクチャの出番です。

# Micro Frontends とは

> それはマイクロサービスの考え方をフロントエンドに拡張したものです。
[https://micro-frontends-japanese.org/resources/monolith-frontback-microservices.png:image=https://micro-frontends-japanese.org/resources/monolith-frontback-microservices.png]
[https://micro-frontends-japanese.org/resources/verticals-headline.png:image=https://micro-frontends-japanese.org/resources/verticals-headline.png]

↓の記事は、とてもわかりやすく参考になりますので、興味がある方は読んでみて下さい。

[https://micro-frontends-japanese.org/:embed:cite]

要は、バックエンドだけでなく、バックエンドからフロントエンドまでをマイクロサービス化することです。

↓の書籍を読むと、

[https://www.manning.com/books/micro-frontends-in-action:embed:cite]

> Amazon does not talk a lot about its internal development structure. However, there are reports that <b>the teams who run its e-commerce site have been working like this </b>for a long time.  ...

> <b>Micro frontends are indeed quite popular in the e-commerce</b> sector.  <b>In 2012</b> the Otto Group, a Germany based mail order company and one of the world’s largest e-commerce players started to split up its monolith.  ...

> The Swedish furniture company <b>IKEA and Zalando</b>, one of Europes biggest fashion retailers, moved to this model. ...

> But micro frontends are also used in other industries. <b>Spotify</b> organizes itself in autonomous end-to-end teams they call Squads. ...

Excerpt From: Michael Geers. “Micro Frontends in Action MEAP V03.” iBooks. 

という説明があります。

IKEAやZalando といったECサイトがMicro Frontendsを採用するケースが多く、公には言っていませんが、AmazonもMicro Frontendsで取り組んでいるようです。
ECサイトだけでなく、Spotifyのようなサービスにも適用されるケースがあります。

# Micro Frontends の良さ

私が思う Micro Frontends から得られる最大の恩恵は、"局所化" だと思います。

フロントエンドをサービス毎(商品、注文、検索など)に分割することで

* サービスの<b>専門性</b>向上
  * ex. 対象サービスのフロントエンドだけに集中する
* サービスの<b>開発速度</b>向上
  * ex. 対象サービスのソースコードだけ読めば良い
  * ex. 対象サービスだけにライブラリアップデートすれば良い
  * ex. フレームワークの切り替えは対象サービスだけすれば良い

少し薄っぺらいかも知れませんが、↑のように実感しています。

※ Micro Frontendsは Webベースのアーキテクチャになります。

# Micro Frontends の悪さ (難しさ)

ここは、まだちゃんと掘り下げれていませんが、次のようなものがあります。

* 特定チームが改善しても、チーム全体が改善しない
  * ex. あるチームがwebpackのビルド時間短縮に成功しても、他のチームは影響を受けない
  * ex. 全てのチームが採用しているライブラリのセキュリティパッチは、それぞれのチームが更新しなければならない
* チーム全体へ共有する仕組みを考える必要がある
  * ex. デザインシステム、パフォーマンス、ナレッジ
* エッジな技術スタック採用は、チームメンバー移動を困難にする
  * ex. パラダイムシフトが発生してしまう 技術スタック

# Micro Frontends の作る上で考えること

フロントエンドをマイクロサービス化するということは、各サービスで HTML/CSS/JSを作ることになります。
それらのサービスを統合するサービスが重要になってきます。

大きく分けて2つの統合パターンがあります。

|種類|解決手段|メリット|デメリット| 
| ---- | ---- | ---- | ---- | 
|サーバーサイド統合| SSI, ESI, Tailor, Podium  |・SEO対策上良い<br>・ユーザーのネットワークレイテンシーが少ない<br>・初回ロードパフォーマンスが優れている|・インタラクションアプローチが不得意|
|クライアントサイド統合|<s>Ajax, Iframe,</s> Web Components  |・Web標準<br>・シャドウDOMによる堅牢な作り|・サポートブラウザに依存する<br>・クライアント側のJavaScriptが有効であること|

また、これら2つの選択基準は次のようになります。

|種類|選択基準|
| ---- | ---- | 
|サーバーサイド統合|良好な読み込みパフォーマンスと検索エンジンのランキングがプロジェクトの優先事項であること|
|クライアントサイド統合|さまざまなチームのユーザーインターフェイスを1つの画面に統合する必要があるインタラクティブなアプリケーションを構築すること|

今回、私はサーバーサイド統合(Podium)を選択しました。
ただ、インタラクティブなアプローチも必要だったため、Hydrationを使ってみました。

> Hydration refers to the client-side process during which Vue takes over the static HTML sent by the server and turns it into dynamic DOM that can react to client-side data changes.

※ [https://ssr.vuejs.org/guide/hydration.html]

Hydrationは、サーバーサイドでレンダリングした静的HTMLに、クライアントサイドの動的レンダリングができるようにするようなものです。

ちなみにWeb Componentsは、↓の入門書を執筆したため、ご興味がある人は見てみて下さい。
[https://silverbirder.booth.pm/items/1572900:embed:cite]

# Micro Frontends　サンプルWebアプリの紹介

<figure class="figure-image figure-image-fotolife" title="Micro Frontends Sample Web Application">[f:id:silverbirder180:20200430213641j:plain]<figcaption>Micro Frontends Sample Web Application</figcaption></figure>
[https://github.com/Silver-birder/trial-web-architecture/tree/master/think2:embed:cite]

# サンプルWebアプリで分かったこと

# 参考にしたもの

[https://github.com/ChristianUlbrich/awesome-microfrontends:embed:cite]

# 最後に
