# AWSを支えるグローバルネットワーク

  # az
アベイラビリティゾーン（１以上のでpたセンターで構成）

  # リージョン
azを複数＋複数のトランジットセンターで構成されるインフラ
ファイバでつないでいる
ex東京リージョン、オレゴンリージョン（usなら）


    # アメリカの事例
コンポーネントが壊れても動くように作っている
usで光ファイバーを切断されてしまったことがある
１３パケットのドロップの被害だった
地中
こうじで

    # ブラジル
電柱
ゴミ捨て場で火災で切断
被害報告なし



  ＃ リージョン内ネットワークの可溶性
休眠しているファイバーをダークファイバーという
→だけど、ちゃんと繋いでいるのでいざという時に役にたつ

位置のトラッキング
光は超多重化を活用している

  ＃リージョン内のネットワーク仮想 / オーバーレイ

    # EC2
Cのインスタンスの歴史

C3以降
AWS Nitro System


    # amazon VPC
クラウドスケールを実現するためにAWSが開発した分散型仮装ネットワーク

インスタンス配置の管理と検証を行う「まっっピングサービス」と転送を行う「部ちりほそとで構成

    # AWS Hyperplane



  # リージョン間のネットワーク
* hawaiki
* bay to bay express 
* jupiter 



* Inter-Region VPC Peering
* Direct Connect Gateway
* AWS Global Accelerator
* Amazon CloudFront
* AWS Shield/AWS WAF


# 本日の内容はここでもまとまってる
https://infrastructure.aws/



















