# About Phalcon
- PHPフレームワーク

## Link
- [Phalcon Docs](https://docs.phalcon.io/3.4/ja-jp/introduction)

## オートローダー
- app/config/loader.php
- アプリケーションが最終的に必要とするクラスを探すディレクトリのセットを登録する
- 設定ファイル(config.ini)で定義されたディレクトリを登録することに注意
- viewsDirにはクラスは含まれないため登録しない
- APP_PATHはpublic/index.phpにて定義され、ルートパスを参照可能
