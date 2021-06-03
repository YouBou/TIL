## 構造に関するパターン
---

### Adapter(Wrapper)

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml24.png)

- 既存クラスのインターフェースを互換性のあるインターフェースに変換する。
- 元のインターフェースを使いつつ、クライアントに異なるインターフェースを提供することで、互換性の点から連携ができないクラスを連携可能にする。
- 継承を利用する場合と委譲を利用する場合がある。
- Wrapperパターンと呼ばれることもある。

### Bridge

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml25.png)

- 抽象化と実装を切り離し、独立した変化を可能にする。
- 切り離される対象は機能クラスと実装クラス
  - 機能クラス：親クラスで基本的な機能を持ち、子クラスで独自機能が追加される
  - 実装クラス：親クラスにて抽象メソッドによるインターフェース定義がされており、子クラスにてインターフェースが実装される。

### Composite

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml26.png)

- Compositeとは"混合物・複合物"を意味し、「容器と中身を同一視する」方式
- 木構造を持つデータに再帰的な処理を行うことが可能