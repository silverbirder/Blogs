# Links


# Title
コロナ禍におけるエンジニアのためのCloud IDE

# Contents
[f:id:silverbirder180:20201211224606p:plain]

2020年3月頃からコロナが流行りだし、もう12月になります。働き方が大きく変わり、リモートワークが当たり前の時代となりました。
エンジニアの働き方も同様に変わりました。そこで、今回、Cloud IDEというものを紹介しようと思います。

[:contents]

# リモートワークとDaaS

[https://www.ascentech.co.jp/solution/column/daas.html:embed:cite]

DaaSのように、クラウド上で開発環境(editor, language runtime, etc)を構築して、
会社所有のノートPCを自宅に持ち帰り、そこからそのクラウドへ接続して仕事をするのは多いのでは。

ただ、その環境を一々作るのって大変ですよね。

# Cloud IDE

Cloud IDEは、クラウド上で統合開発環境(IDE)のことで、主にブラウザから操作できるようなものが多いです。

GCP:Cloud Shell Editor
AWS:Cloud9
Microsoft:VisualStudio Codespaces
Github:Codespaces

Gitpod
Coder

この中で、GCPやGitpodのCloud IDEは、OSSのTheiaを使っています。

# Theia

[https://github.com/theia-ide/theia-apps]
[https://github.com/eclipse-theia/theia]
[https://docs.google.com/document/d/1aodR1LJEF_zu7xBis2MjpHRyv7JKJzW7EWI9XRYCt48:title]

OSSです。つまり誰でも使えます。VMインスタンスにTheiaを入れれば、独自に運用できます。
つまりベンダーニュートラルです。

# デメリット

遅延。
ブラウザのキーマッピング。

# 個人的な話

個人的な開発環境に、Gitpodを使いたいのですが無料だと月50時間までしか使えません。
"Professional Open Source" というものを応募したところ、Gitpodの組織(https://github.com/gitpod-io) へ招待頂き、公開リポジトリの無制限利用ができるようになりました。