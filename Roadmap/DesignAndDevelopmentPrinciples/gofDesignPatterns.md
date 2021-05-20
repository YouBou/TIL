## GOF
---

## 生成に関するパターン
---
### Abstract Factory
![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml13.png)
- 抽象的な工場
- 具体的な実装に意識を向けず、インターフェイスに注視する状態
- 具体的なFactoryを追加する場合、各interfaceを実装することになり結果としてパッケージ内のimplementsするだけに留まる。