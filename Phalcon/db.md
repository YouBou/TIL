# Phalcon\Db
---
- [Github](https://github.com/phalcon/cphalcon/tree/v3.4.0/phalcon/db.zep)
- [Document](https://docs.phalcon.io/3.4/en/api/phalcon_db)

## 概要
- PHPアプリケーションをRDBMSに接続するために使用する基本クラス
- このコンポーネントは低レベルのDB操作を目的としている
- より高レベルのDB対話をする場合はPhalcon\Mvc\Modelを使う
- Phalcon\Dbは抽象クラスで、Phalcon\Db\Adapter\Pdoなどのデータベースアダプタのみで使用可能

## Source
```php
 <?php
 use Phalcon\Db;
 use Phalcon\Db\Exception;
 use Phalcon\Db\Adapter\Pdo\Mysql as MysqlConnection;

 try {
     $connection = new MysqlConnection(
         [
             "host" => "192.168.0.11",
             "username" => "sigma",
             "password" => "secret",
             "dbname"   => "blog",
             "port" => "3306",
         ]
     );

     $result = $connection->query(
         "SELECT * FROM robots LIMIT 5"
     );

     $result->setFetchMode(Db::FETCH_NUM);

     while ($robot = $result->fetch()) {
         print_r($robot);
     }
 } catch (Exception $e) {
     echo $e->getMessage(), PHP_EOL;
 }
```

## Methods
- **public boolean insert(string arg)**
  - array \$table, array \$values, [array \$fields], [array \$dataTypes]
```php
<?php

// Inserting a new robot
$success = $connection->insert(
    "robots",
    ["Astro Boy", 1952],
    ["name", "year"]
);
```
```sql
-- Next SQL sentence is sent to the database system
INSERT INTO `robots` (`name`, `year`)  VALUES ("Astro Boy", 1952);
```

- **public boolean update(string arg)**
  - array \$table, attay \$fields, array \$values, [string array \$whereCondition], [array \$dataTypes]
```php
<?php

// Updating existing robot
$success = $connection->update(
    "robots",
    ["name"],
    ["New Astro Boy"],
    "id = 101"
);
```
```sql
-- Next SQL sentence is sent to the database system
UPDATE `robots` SET `name` = "Astro boy" WHERE id = 101
```

- **public boolean delete (string arg)**
  - array \$table, [string \$whereCondition], [array \$placeholders], [array \$dataTypes]
```php
<?php

// Deleting existing robot
$success = $connection->delete(
    "robots",
    "id = 101"
);
```
```sql
-- Next SQL sentence is generated
DELETE FROM `robots` WHERE `id` = 101
```