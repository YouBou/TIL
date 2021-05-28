## GOF
---

## 生成に関するパターン
---
### Abstract Factory

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml13.png)

- 抽象的な工場という意味
- 具体的な実装に意識を向けず、インターフェイスに注視する状態
- 具体的なFactoryを追加する場合、各interfaceを実装することになり結果としてパッケージ内のimplementsするだけに留まる。

### Buider

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml14.png)

- 複雑な構造を構築する場合、各部分毎に小規模なパーツを構築した上で目的となる構造を組み上げる
- オブジェクトを組み合わせ、複雑なオブジェクトを構築するインターフェースをBuiderクラスと呼ぶ

### Factory Method

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml15.png)

- インスタンス作成方法をスーパークラスで定め、具体的な処理はサブクラス側に担わせる方式
- SOLIDの5原則の"D"にあたる「依存性逆転の法則(Dependency Inversion principle)」を実現するためのパターン
- FactoryMethodクラスは抽象クラスに依存する

### Object Pool

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml16.png)

- 作成したオブジェクトを利用後に破棄するのではなく、再利用するための方式
- インスタンスの初期化に高コストが掛かる場合やインスタンス化させる割合が大きい場合にパフォーマンス向上に寄与できる
- しかし、外部リソースを保持せずメモリ占有のみの場合は逆にパフォーマンス低下の可能性もある

### Prototype

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml17.png)

- オブジェクトの新規生成コストを抑えるため、プロトタイプを作成した上でコピー(clone)により生成する方式
- インスタンス生成に複雑な処理を必要とする場合や時間がかかる場合、`new hoge()`による生成は非効率
- `new hoge()`による生成はPrototypeのみで行い、以降はcloneによる生成で賄う

### Simple Factory

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml18.png)

- Static Factoryパターンとは異なる
- 異なるパラメータの複数factoryを持つことが可能
- 使用優先度的にはStatic Factoryよりも高い