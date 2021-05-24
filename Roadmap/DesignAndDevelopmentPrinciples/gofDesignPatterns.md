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