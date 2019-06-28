# Serverless/AppSync によるモバイル開発の今


## Serverlessとは
---

* Serverlessは次の特徴を持つものである
    * インフラのメンテが不要
    * オートスケールする
    * 価値に対して支払いを行うものである
        * 利用した時間分だけ支払う（Pay-as-you-go）
        * ハードウェアではなくてスループットに支払うものと言える
    * 高可用性・セキュアである


## AppSyncとは
---

AmazonのマネージドGraphQLサービスである

GraphQL APIとREST APIの違い。例えばどのようなものがあるか？

* 「post」「comments」「authors」の三つの種類のデータを取得する機能をAPIで提供したいケースがあったとす、
    * REST APIの場合  
  /post /comments /authors それぞれに1つづつエンドポイントを用意することになり、3回もNWコールが必要
    * GraphQL APIの場合  
  /graphql 1回のみNWコールが必要

AppSyncの主な特徴のまとめ

* マネージドサービスであること
* データソースの連携先が豊富なこと
    * Amazon DynamoDB
    * Amazon Aurora
    * Elasticsearch
    * AWS Lambda
    * 任意のHTTP Endpoint
* Subscribeによってリアルタイムで変更通知を受けられること


## Gunosyの人登場  
---

グノシースポーツを作ったときの話  

### リアルタイム更新を行いたかったからAppSyncを採用

いくつかある課題課題の中で

* バックエンド開発において、リアルタイム通信の実現のためには同様の処理を二つ書く必要が生じていた
* フロントエンド開発において、こちらも同様に処理を二つ書く必要が生じていた

楽になったこと

* データ取得時にDynamoDBに書きこみするだけでリアルタイム通知が実現できる
* フロントエンド側でも対応は必要だが、Apollo のsdkを入れることで比較的簡単に実装できる
* 通常のクエリとリアルタイムのデータ取得を、一つのソースで実現できる
* Appsyncはスキーマファーストで進められる（逆に、スキーマが決まらないとそこから進めない）
* CloudFormationでGraphQlのスキーマを管理できる
* これにより最新版は常にGitにある、という運用が可能
* 従来のように同じようなソースを二つ用意するケースが減る

AppSyncを使ってみてのTips

* GSIで頑張らずにElasticsearchに入れる
* 並び替えや部分一致に柔軟に対応できる
* 各CloudFormationテンプレ内で頑張らないようにする
* 1ファイルが長くなりがちなので、分割する


## ライブコーディングのデモ
---

突然アプリを作る展開になった

わずか数回のコマンド、数行の追加でreactのTODOアプリを動かすサンプルを作る

* reactアプリケーション
* amplifyをインストール
* amplify add API
* ここでGRAPHQLを選ぶ
    * amplifyでスキーマの設定を行います
* reactのapp.js
* import aws_config
* import auth
* import withAuthencicator, SingOut
* export default withAuthenticator(App)

### awsのコンソール

ログインして、スキーマ、クエリを見て確認。


## 最後に
---

amplifyはオープンソースなのでAWSの社員以外も積極的に機能追加してくれている  
⇒amplifyはいいぞー



