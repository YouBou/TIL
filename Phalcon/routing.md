# Routing
---
- RouterにはMVCモードとマッチオンリーモードの2つがある
## MVC MODE
- ルートを定義し、必要なController/Actionと結びつけることができる
- Router自体はController/Actionを実行しない
- Routerは情報を収集し、Controller/Actionを実行する役割を持つComponentに渡す

```php
<?php

use Phalcon\Mvc\Router;

// ルーターの作成
$router = new Router();

// ルートを定義
$router->add(
    '/admin/users/my-profile',
    [
        'controller' => 'users',
        'action'     => 'profile',
    ]
);

// 別のルート
$router->add(
    '/admin/users/change-password',
    [
        'controller' => 'users',
        'action'     => 'changePassword',
    ]
);

$router->handle();
```

- アプリケーションには多くのパスが想定されるため、ルートを1つずつ定義するのは大変
- より柔軟なRouteを作ることができる

---

```php
<?php

use Phalcon\Mvc\Router;

// ルーターの初期化
$router = new Router();

// ルートの定義
$router->add(
    "/admin/:controller/a/:action/:params"
    [
        "controller" => 1,
        "action" => 2,
        "params" =>3,
    ]
)
```

- add()メソッドは、定義済みプレースホルダーや、正規表現修飾子をパターンとして受け取ることができる
- 全てのRoutingパターンはスラッシュから始める必要がある
- 正規表現のデリミタ(区切り文字)を付ける必要はない
- 全てのRouteパターンは文字の大小を区別する

|Placeholder|Regular Expression|Usage|
|:---|:---|:---|
|/:module|/([a-zA-Z0-9\_\-]+)|有効なモジュール名と英数字のみを照合させます|
|/:controller|/([a-zA-Z0-9\_\-]+)|有効なコントローラー名と英数字のみを照合します|
|/:action|/([a-zA-Z0-9\_]+)|有効なアクション名と英数字のみで照合します|
|/:params|(/.\*)\*|/で区切られたオプションの単語のリストに一致します  このプレースホルダーはルートの最後でのみ使用してください|
|/:namespace|/([a-zA-Z0-9\_\-]+)|単一レベルの名前空間名と一致します|
|/:int|/([0-9]+)|整数パラメータに一致します|
- Controller名はキャメルケースに変換される
- some_controller → **SomeController**
- ルートが追加された順番が関連性を示す
  - 後で追加されたルートの方が優先して適用
  - 全ての定義済みルートは、追加された順番とは逆順にマッチングが行われ
    Phalcon\Mvc\Routerが与えられたURIに適合するルートを見つけると、残りは無視される
