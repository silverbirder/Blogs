# Links
TBD

# Title
Google Apps Script でも テスト がしたい！

# Contents
## Google Apps Scriptのテストってどうしてますか？


## 雑感(書く内容メモ)

* Google Apps Scriptのテストがやっかい
  * わざわざブラウザエディタひらいて、デバッグ実行。面倒
  * 連携サービスに依存するため、結果が不安定。何が原因か調べる大変
  * ストレスフル！！！
* Clasp + TypeScript + Jest でローカルテスト 
  * ImplをMockで差し替えてテスト
  * ストレスフリー
* 実際にライブラリを作ってみた
  * CaATは、GoogleCalendarの予定時間をカスタマイズして計算できるライブラリ
  * https://www.npmjs.com/package/@silverbirder/caat
  * https://github.com/Silver-birder/caat
  * https://github.com/Silver-birder/SampleCaat
