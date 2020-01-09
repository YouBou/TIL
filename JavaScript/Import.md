# import
- [mozilla - import](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Statements/import)
- [qiita - ES6モジュールのインポートとエクスポート](https://qiita.com/dondoko-susumu/items/55f54582d31b0f0fd687)
- 他のモジュールからexportされたバインディングをimportするために用いる
- **静的なimport**
  - モジュールのトップレベル以外には書けない
  - if文,関数の中に書くとエラー
- **動的なimport**(Dynamic Import)
  - 関数としてimportを呼び出す
  - Promiseを返す
  - トップレベル以外でも書ける

>*import defaultExport from "module-name";*
*import * as name from "module-name";
import { export } from "module-name";
import { export as alias } from "module-name";
import { export1 , export2 } from "module-name";
import { export1 , export2 as alias2 , [...] } from "module-name";
import defaultExport, { export [ , [...] ] } from "module-name";
import defaultExport, * as name from "module-name";
import "module-name";*
>*var promise = import(module-name);*

