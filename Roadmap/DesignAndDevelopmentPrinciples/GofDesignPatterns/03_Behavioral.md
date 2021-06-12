## 振る舞いに関するパターン
---

### Chain Of Responsibilities

![](https://designpatternsphp.readthedocs.io/ja/latest/_images/uml.png)

- 複数のオブジェクトを連鎖的に繋いでおき、各オブジェクトを順次チェックすることで目的のオブジェクトを決定する方式
- 各クラスが持つ責務を限定的に分割できるため、必要に応じて連鎖させる流れの変更が容易となる
- どの状況でも各クラスをチェックしていくため、パフォーマンスの劣化の可能性がある

