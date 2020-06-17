# Links
TODO

# Title
Webアプリのテスト観点を調べてまとめてみた

最近、Property Based Test という言葉を知りました。
他にどういうテストの種類があるのか気になったので、調べてみました。
本記事は、テストの種類を列挙します。

[:contents]
# テスト一覧
## Bot Test
TODO

## Code Size Test

大きなサイズ (ex. 10kb以上)のJSライブラリを読み込むと、ブラウザ側のレスポンスタイムが悪化してしまいます。そこで、常にコードサイズを計測する必要があります。

[https://github.com/ai/size-limit:embed:cite]
<figure class="figure-image figure-image-fotolife" title="https://github.com/ai/size-limit">[f:id:silverbirder180:20200617070042p:plain]<figcaption>https://github.com/ai/size-limit</figcaption></figure>

## Complexity Test

循環的複雑度(Cyclomatic complexity)は、ソースコードの制御文(ifやfor)の複雑さを計測します。

[https://eslint.org/docs/rules/complexity:embed:cite]

## Copy&Paste Test

Copy&Pasteは、DRYの原則に反するため、特別な理由がない限りは、してはいけません。Copy&Pasteを検出するツールがあるみたいです。

[https://github.com/kucherenko/jscpd:embed:cite]
<figure class="figure-image figure-image-fotolife" title="https://github.com/kucherenko/jscpd">[f:id:silverbirder180:20200617070137p:plain]<figcaption>https://github.com/kucherenko/jscpd</figcaption></figure>

## Cross Browser/Platform Test

サポートするブラウザや、プラットフォーム（iOS,Android,Desktopなど)の動作検証が必要です。

[https://github.com/browserstack:embed:cite]

## E2E Test

Webアプリを、端から端まで (End To End: E2E)を検証します。
例えば、ユーザーがWebアプリを訪れて、クリックや入力し使ってみることです。

[https://github.com/cypress-io/cypress:embed:cite]

## Exception Test
## Flaky Test

不安定なテストのことを指します。これに対するアプローチ方法の１つに、Google社の資料があります。

[https://static.googleusercontent.com/media/research.google.com/ja//pubs/archive/45880.pdf]

日本人がまとめて頂いたものが、次のものです。
[https://speakerdeck.com/nihonbuson/flakytests:embed:cite]

## Integration Test
## Logging Test
## Monkey Test

お猿さんがランダムにテストするような、モンキーテストです。
テストのパターン網羅が難しい場合や、パターン網羅できているけどダメ押しで、このテストをします。

[https://github.com/marmelab/gremlins.js/:embed:cite]
<figure class="figure-image figure-image-fotolife" title="https://github.com/marmelab/gremlins.js">[f:id:silverbirder180:20200617070229g:plain]<figcaption>https://github.com/marmelab/gremlins.js</figcaption></figure>

## Multi Tenanct Test
## Mutation Test

テストを検証するため、突然変異テストというものがあります。(カオスエンジニアリングに近いかもしれません）
プロダクトコードを破壊することで、テストがどうなるのかを検証します。

[https://github.com/stryker-mutator/stryker:embed:cite]
<figure class="figure-image figure-image-fotolife" title="https://stryker-mutator.io/stryker/quickstart">[f:id:silverbirder180:20200617070455g:plain]<figcaption>https://stryker-mutator.io/stryker/quickstart</figcaption></figure>

## Performance Test

パフォーマンスと言っても、
CPU使用率、メモリ使用率、レスポンスタイム、RPS など様々な指標があります。
これらを計測し、SLOなどの基準値を満たせているかを検証しておく必要があります。

[https://github.com/bestiejs/benchmark.js/:embed:cite]

## Property Based Test

データを半自動生成し、テストをする手法です。

[https://github.com/dubzzz/fast-check:embed:cite]

## Regression Test
## Robustness Test
## Security Test

npm audit fix

## SEO Test

[https://github.com/GoogleChrome/lighthouse-ci:embed:cite]

## Smoke Test



## Snapshot Test

[https://jestjs.io/docs/ja/snapshot-testing:embed:cite]

## Static Test
  * Danger 
  * https://gist.github.com/Silver-birder/71135913192fbca51a7e26924bd36b8b

## Unit Test

[https://github.com/facebook/jest:embed:cite]

### Code Coverage

[https://jestjs.io/docs/en/cli.html#--coverageboolean:title]

## Visual Regression Test

見た目の変化を監視する必要があります。例えば、リンク切れとかがあれば、検出するべきです。

[https://github.com/garris/BackstopJS:embed:cite]
<figure class="figure-image figure-image-fotolife" title="https://github.com/garris/BackstopJS">[f:id:silverbirder180:20200617070556p:plain]<figcaption>https://github.com/garris/BackstopJS</figcaption></figure>

# 最後に