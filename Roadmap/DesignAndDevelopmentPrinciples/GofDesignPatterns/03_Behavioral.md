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