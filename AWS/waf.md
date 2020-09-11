## AWS WAF
- **AWS WAF**
  - AWSが提供する**WAF**(**W**eb **A**pplication **F**irewall)
  - HTTP(80)/HTTPS(443)アプリケーション層の防御
  - Web ACLを用いてアクセス制御する
  - SQLインジェクション, XSS, アプリケーション固有の攻撃に対応
- **Web ACL**
  - WebACLリストでRulesを紐づける
  - 1つのWebACLに適用可能なRuleは10個まで
  - CloudFront, ALB, APIGatewayにWebACLを関連付けて利用
- **Rules**
  - 具体的な条件を指定する**Conditions**を紐付けて管理
  - 1Ruleに対して適用可能なConditionは10個まで
- **Conditions**
  - 防ぎたい攻撃条件を具体的に定義
  - SQLインジェクション, XSS等のConditionが用意
  - アプリケーション固有の攻撃に対応する場合は独自の条件を記述

## AWS WAFによる防御手順
1. アクセス制御目的に合わせCondition作成
2. 作成したConditionを含むRule作成
3. 作成したRuleを適用するためのWeb ACL作成
4. 作成したRuleをWeb ACLに適用
5. Web ACLをCloudFront, ALB, API Gatewayのいずれかに適用

## AWS WCU(Web ACL Capacity Units)
- Rule, RuleGroup及び、Web ACLの実行に必要な操作リソースを計算・制御する
- 実行コストが少ない単純なRuleはより多くの処理を必要とするRuleよりも少ないWCUを使用する
  - サイズ制約 < 正規表現パターン
- Web ACLの最大容量は**1,500**で上限緩和(料金UP)あり

## ACL(Access Controll List)
- ネットワーク上のリソースへのアクセス制御設定をリストとして列挙したもの
- 宛先・送信元IP及びportを条件とし、それに合致した通信可否をACLとして設定
  - 特定サーバのIP宛のパケットのみを許可とか
  - 特定の送信元IPからのパケットはすべて破棄など...

### 参考
- [Waf Charm "AWS WAF 解説 【第1回 基本構造編】"](https://www.wafcharm.com/blog/aws-waf-basic-structure/)
- [AWS WAF Web ACL capacity units(WCU)](https://docs.aws.amazon.com/ja_jp/waf/latest/developerguide/how-aws-waf-works.html)
- [NTT ICT Business Online "ACLとは"](https://www.ntt.com/bizon/glossary/e-a/acl.html)