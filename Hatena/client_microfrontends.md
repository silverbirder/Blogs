# Links


# Title
クライアントサイド(ES Module)でMicro Frontends

# Contents
ArchUnitをというものを最近知りました。依存関係のテストができるそうです。さっそく試してみたいと思いますので、その備忘録として残しておきます。

[:contents]
2021年、あけましておめでとうございます。本年も宜しくおねがいします。最近は、自身のポートフォリオページを刷新しようと試みています。
本記事は、昨年の冬あたりで検証していた クライアントサイド統合でのMicro Frontendsにチャレンジしていました。その内容を思い出しつつ、記録を残したいと思います。

[:contents]

# 概要

全体設計は、次の画像のとおりです。

![overview](https://raw.githubusercontent.com/Silver-birder/micro-frontends-sample-code-6/main/overview.svg)

App Shell

# Tips
App Shell の設計。

scriptをloadする際、es module をimportするようにしているので、javascriptがes moduleでかける ( import)。

コンポーネントを見つけるAPI、Discovery APIが大切。

Componentは、Web ComponentsであるLit Elementを採用しているので、CSSのスコープは独立している。

Routerは、valian routerが使いやすい。
Workerは、es module workerを使って、メインスレッド以外で動かす細かなことをしようとしていた。（使っていない）

コンポーネント同士を独立させたい。

発想が変わらないせいなのか、クライアントサイドだろうがサーバーサイドだろうが、おおよそのMicro Frontendsの構成や役割は、そう変わらないなと...。
