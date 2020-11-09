# Links

# Title
Cloudflare Workers (Edge Worker) で Micro Frontends

# Contents
こんにちは

[:contents]

# Tips

* Edgeの制約がある
  * 同一ドメイン内でのEdge Worker通信が不可
     * 複数ドメインが必要
  * 直接IPを使えないため、ローカル開発では一工夫必要
  * Edge で使えるモジュールは限定的
  * HTML Rewriter よき
* Lit-Element + Apollo Client のproduct と test コード共存に苦しんだ
* 
