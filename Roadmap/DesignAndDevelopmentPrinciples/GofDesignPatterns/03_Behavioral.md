## 振る舞いに関するパターン
---

### Chain Of Responsibilities

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml.png)

- 複数のオブジェクトを連鎖的に繋いでおき、各オブジェクトを順次チェックすることで目的のオブジェクトを決定する方式
- 各クラスが持つ責務を限定的に分割できるため、必要に応じて連鎖させる流れの変更が容易となる
- どの状況でも各クラスをチェックしていくため、パフォーマンスの劣化の可能性がある

### Command

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml1.png)

- 命令を表すクラスのインスタンスを単一のものとして表現する方式
- オブジェクトに対して送る要求をオブジェクト化することで、メソッドを呼び出す場合の引数等の拡張に囚われる必要性が抑えられる
- 機能拡張を行う場合は命令のベースとなるインターフェースを作成するに留まるため、拡張性も担保される

### Interpreter

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml2.png)

- Interpreterは「解釈者・説明者」を意味する
- 実装言語とは異なるフォーマットで記載された命令を解析し、言語の文法をオブジェクトで表現するパターン
- 主な目的
  - プログラムを外部から動的に制御可能な仕組みの実現
  - 特定ドメインで問題を高効率で解決するため(SQl等)

### Iterator

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml3.png)

- Iteratorは「繰り返し」を意味する
- 要素の集合(配列)を保持するオブジェクトの各要素に対して順番にアクセスする方式
- 集合を表現するList系クラスとは独立させた形でListに対する走査方法を表現するクラスを置く
- ドメイン部分となる実装と切り離しておくことでList系クラスに変更が加わった場合の変更点を抑えられる

### Mediator

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml4.png)

- Mediatorは「仲裁人・調停者」を意味する
- 複数オブジェクト間の調整役として各オブジェクトからの問合せを受け、必要に応じた判断と指示を出す
- 調整役となるMediator Interfaceと問合せ側となるColleague Interfaceからなる

### Memento

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml5.png)

- Mementoは「記念品・形見」を意味する
- インスタンスのある状態をスナップショットとして保存しておくことで、その時点でのインスタンスの状態に復元することを可能にする方式
- インスタンスを復元可能にするために不用意なアクセスを許容してしまうとカプセル化の破壊に繋がる
- 状態を表現する役割を設けておくことで、修正に伴うスコープを限定できる

### Null Object

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml6.png)

- 厳密にはこの方式はGoFに含まれないが、デザインパターンとして扱うのに十分な頻度で用いられている
- あるオブジェクトがnullでなければメソッドを呼び出す場合にnullによる判定ではなく、何も行わないオブジェクトを格納する
- ある状況下でオブジェクトが生成されなかった場合の挙動を意識する必要が無くなる

### Observer

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml7.png)

- Observerとは「観察者」を意味する
- 状態が変化する側が観察者に対して通知する仕組みを持つことで、観察者側が常に対象の状態変化を監視する必要を避ける方式
- Mediatorパターンでも利用される

### Specification

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml8.png)

- Specificationは「仕様」を意味する
- Gofのパターンには含まれていないが、DDD本の中で触れられている方式
- エンティティやコレクションに対して、ある条件を満たすものを抽出したい等の場面で用いられる
- このような判定をビジネスルール上にメソッドとして表現するのではなく、各条件による判定をオブジェクトとして表現する
- こうした条件を括り出しておくことで再利用性を高めることができる
- 簡易な条件の場合はif文による表現でも問題ない場面もあるため、複雑な条件が求められるほど効果的となる

### State

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml9.png)

- Stateは「状態」を意味する
- 状態によって振る舞いが変化する状況下において、状態をクラスとして表現・切り替えを行う事で「状態変化」を表す方式
- 状態を表すinterfaceと具体的な状態をimplements先で表現する
- 1状態の表現に複数オブジェクトは不要なため、Singletonパターンを利用する
- 1状態1オブジェクトでの表現のため、他の状態を意識した実装を行う必要が無くなる
- 求められる状態が多ければ多いほど有効な手段となる

### Strategy

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml10.png)

- Strategyは「戦略」を意味する
- メソッド内での条件分岐によるアルゴリズムの変更ではなく、クラス単位での切り替えで対応する方式
- クラス単位での切り分けによる複雑さよりも、疎結合による柔軟さが効果的に働く