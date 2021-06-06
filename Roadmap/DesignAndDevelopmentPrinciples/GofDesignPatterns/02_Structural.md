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

### DataMapper

![](https://designpatternsphp.readthedocs.io/en/latest/_images/uml27.png)

- データストア(主にRDB)とインメモリでのデータ表現との間でデータの双方向転送を実施するアクセスレイヤー
- インメモリでの表現とデータストアをそれぞれ、データマッパー自体から独立させておく
- レイヤーはデータ転送を実施する1つ以上のマッパー(DAOとか)で構成される。
- ActiveRecordパターンとは異なり、データモデルが単一責任の原則(SOLID:S)

### Decorator

![](https://designpatternsphp.readthedocs.io/en/latest/_images/uml28.png)

- 既存のオブジェクトに対して新たな機能やふるまいを動的に追加することを可能にする方式
- `Decorator`クラスのコンストラクタでラップ対象のオブジェクトを受け取り、メンバとして扱うのが一般的
- 既存クラスの拡張時に、継承に代わる手段として用いられる

### Dependency Injection

![](https://designpatternsphp.readthedocs.io/en/latest/_images/uml29.png)

- 一般的に"DI：依存性の注入"と呼ばれる
- クラスやメソッド内に固有の値を持たせた依存性の形に対して、依存している固有の値を外部から渡す(注入)方式
- Interface Injection, Constructor Injection, Setter Injectionなどがある
- モジュール間が疎結合となり保守性が高まる
- DIを採用しない場合にくらべファイル数は増加する