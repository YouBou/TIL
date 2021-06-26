### Service Locator

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml23.png)

- 依存性逆転の原則に違反する形のため、アンチパターンと見做される場合もある
- 依存性注入を使用する場合のようにクラスの依存関係を公開するのではなく、非表示にする。

### Repository

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml22.png)

- DDD(ドメイン駆動設計)の一つとして導入されたもので、データソースへのアクセスの抽象化を提供する
- 異なる性質を持つデータソースに対して共通のinterfaceを定義、それをリポジトリとして実装する
- それにより、ビジネスロジックからデータアクセスを分離させ、疎結合の状態とすることで機能としての拡張性・保守性を向上させる