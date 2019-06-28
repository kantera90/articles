

# 【初級】AWSストレージサービス入門

AWSはS3が最初にリリースされた（S3から始まった)

## アジェンダ
---
本セッションの内容
サービス概要
特徴的な機能ユースケース


## Amazon Elastic Block Storage（EBS）
---

* EC2向けの永続的なブロックストレージ
* Elastic Volumes
    * ボリュームタイプの変更ができる


## Amazon Elastic File System（EFS）
---

フルマネージド型クラウドファイルシステム

ライフサイクルポリシーを設定でき、ストレージクラスを自動的に変更できる
コストバランスに気を使える


## Amazon FSx
---

Windowsワークロード
Amazon FSx for Windows File Server


## Amazon FSx for Lustre
---

* S3 へのシームレスなアクセス
* S3 オブジェクトをファイルとして透過的に表示
* AWS S3 に保存したデータを Amazon FSx にインポート
* 処理結果を保存するために AWS S3 にエクスポート


## Amazon S3
---

どこからでもデータの保存と取得ができるオブジェクトストレージ

オブジェクトのネーミングスキーマ
s3://ExampleAWSbucket/Logistics/packing-list.pdf

* ストレージクラスはEFSと同様
* クロスリージョンレプリケート
* データレイクとして使うことができるのが熱い


## 適材適所の選択
---

* ブロックストレージ: EBS
* ファイルストレージ: FSx
* オブジェクトストレージ: S3


