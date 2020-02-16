# Links

# Title
アマゾンの配送予定のようなGMailをGCalendarに登録するサービス rMinc を作ってみた

# ターゲットユーザー

* GMailとGCalendarを使っている人

# メールを開くって面倒じゃないですか？

例えば、次のようなケースがあったとします。

* アマゾンで商品を購入した際、お届け予定日が記載されたメールが届く。
* 映画館(TOHOシネマ)でネット予約した際、上映日が記載されたメールが届く。
* ホテルをネット予約した際、宿泊日が記載されたメールが届く。

私は、これらの情報（日付）をカレンダーに登録しています。
Googleは、気を利かせて、次のようなスケジュールを勝手に登録してくれます。（良い悪いがありますが...）

<figure class="figure-image figure-image-fotolife" title="unknownorganizer@calendar.google.com">[f:id:silverbirder180:20200216115925p:plain]<figcaption>unknownorganizer@calendar.google.com</figcaption></figure>

で、この気を利かせるかどうかは、Googleの判断によるため未知数です。

私は、アマゾンのお届け予定日も、同様のことが勝手にしてくれたら良いな〜と思っていました。

# そこでrMincというツールを作りました
[https://www.npmjs.com/package/@silverbirder/rminc:embed:cite]

概要はこんなかんじ。
![overview](https://res.cloudinary.com/silverbirder/image/upload/v1581769421/rMinc/rMinc_overview.png)

実際に使ってみるとこんなかんじ。
![example](https://res.cloudinary.com/silverbirder/image/upload/v1581760683/rMinc/rMinc_sample.png)

# さいごに
やっぱ、自動化って最高だね。これでメールを開かず、カレンダーにいつ届くのかわかります。