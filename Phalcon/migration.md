# Migration
---
- 各マイグレーションはそれに関連するバージョン識別子を持つ
- DevToolsではデフォルトでapp/migrationsディレクトリを使う
- 各バージョンのディレクトリ配下に各テーブルごとのクラスを持つ

## 初期のマイグレーションファイルを生成

```$ phalcon migration generate```
- ```app/migrations/1.0.0```が作成される
- これには全てのテーブル情報が含まれる

## マイグレーションファイル

```php
<?php

use Phalcon\Db\Column;
use Phalcon\Db\Index;
use Phalcon\Db\Reference;
use Phalcon\Mvc\Model\Migration;

class TablesMigration_100 extends Migration
{
    public function morph()
    {

    }

    public function up()
    {

    }

    public function down()
    {
        
    }
}
```
- マイグレーション処理の走り方
  - ```run```の場合：```morph() -> up()```
  - ```rollback```の場合：```down() -> morph()```

## マイグレーションの実行
```$ phalcon migration run```
- ```... run --version=1.x.x```
  - 指定バージョンのマイグレーション実行