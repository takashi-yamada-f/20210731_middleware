# サーバーサイドのミドルウェアについて

* AmazonがCEO交代。創業者ベゾス氏は会長に（2021年2月3日 10:52）
<br>https://pc.watch.impress.co.jp/docs/news/1304160.html

改めて、WEBアプリケーション開発で利用できるミドルウェアについて、AWSのサービスもあわせて、復習がてら見ていきましょう。

## 【１】ミドルウェアの種類

### (1)WEBサーバー
* Apacheとは - IT用語辞典 e-Words <br>https://e-words.jp/w/Apache.html
* nginxとは - IT用語辞典 e-Words <br>https://e-words.jp/w/nginx.html

### (2)DB
* Oracleとは - IT用語辞典 e-Words <br>https://e-words.jp/w/Oracle.html
* MySQLとは - IT用語辞典 e-Words <br>https://e-words.jp/w/MySQL.html
* PostgreSQLとは - IT用語辞典 e-Words <br>https://e-words.jp/w/PostgreSQL.html
* MariaDBとは - IT用語辞典 e-Words <br>https://e-words.jp/w/MariaDB.html
* SQL Serverとは - IT用語辞典 e-Words <br>https://e-words.jp/w/SQL_Server.html

* AWS RDS <br>https://aws.amazon.com/jp/rds/
* AWS Auroa <br>https://aws.amazon.com/jp/rds/aurora
<br>余談　「uroraかRDSどちらを選ぶべきか」
<br>https://dev.classmethod.jp/articles/developers-io-2019-in-osaka-aurora-or-rds/#toc-rdsaurora

### (3)NoSQL DB
* memcachedとは - IT用語辞典 e-Words <br>https://e-words.jp/w/memcached.html
* MongoDBとは - IT用語辞典 e-Words <br>https://e-words.jp/w/MongoDB.html
* Redisとは - IT用語辞典 e-Words <br>https://e-words.jp/w/Redis.html
<br>Redisクラスタ構築とフェイルオーバー検証 
<br>https://qiita.com/yuuman/items/bf58a89a8e777ce81530
* AWS Elastic cache <br>https://aws.amazon.com/jp/elasticache/
* Amazon DynamoDB <br>https://aws.amazon.com/jp/dynamodb/

### (4)DNS
* BINDとは - IT用語辞典 e-Words <br>https://e-words.jp/w/BIND.html
* AWS Route53 <br>https://aws.amazon.com/jp/route53/

### (5)検索エンジン
* Apache Solrとは - IT用語辞典 e-Words <br>https://e-words.jp/w/Apache_Solr.html
* Apache_Luceneとは - IT用語辞典 e-Words <br>https://ja.wikipedia.org/wiki/Apache_Lucene
* Groonga とは？ <br>https://openstandia.jp/oss_info/groonga/
* Elasticsearchとは - IT用語辞典 e-Words <br>https://e-words.jp/w/Elasticsearch.html
* AWS Amazon Elasticsearch Service <br>https://aws.amazon.com/jp/elasticsearch-service/
* Amazon CloudSearch <br>https://aws.amazon.com/jp/cloudsearch/
<br>インフラの技術選定の失敗は高くつくよという話（ElasticSearchとCloudSearch編）
<br>https://qiita.com/yamotuki/items/e3d9e1cec0d3a5a84dfd

### (6)NFS
* NFSとは - IT用語辞典 e-Words <br>https://e-words.jp/w/NFS.html
* AWS EFS <br>https://aws.amazon.com/jp/efs/

## 【１】Linuxサーバーへの導入

### (1)パッケージ管理
* yumとは - IT用語辞典 e-Words <br>https://e-words.jp/w/yum.html
* RPMとは - IT用語辞典 e-Words <br>https://e-words.jp/w/RPM-2.html
* APTとは - IT用語辞典 e-Words <br>https://e-words.jp/w/APT.html

### (2)導入

* コンパイルして、インストール。指定したバージョンを使わなければならない場合などに使用。
<br>configure, make, make install とは何か
<br>https://qiita.com/chihiro/items/f270744d7e09c58a50a5

* パッケージマネージャーでインストール
```
$ rpm -ivh <パッケージ名>
$ yum install <パッケージ名>
$ apt-get install <パッケージ名>
```
インストールがエラーで中断。どうする？
<br>エラーメッセージを確認する。googleで検索して対処方法を検討する。
<br>依存性を解決できないパッケージを削除する、足りないパッケージを追加する等の作業を、
<br>インストールが成功するまで続ける、、そうすれば大概うまくいく。

### (3)起動
* （CentOS7以前の話）Service start / stop / restart / status
<br>https://www.infraeye.com/study/linuxz56.html
* CentOS7でのサービス（デーモン）の起動・停止方法
<br>https://www.server-memo.net/centos-settings/centos7/service-start.html
* Debianでのサービスの停止、開始、再起動
<br>https://opensofty.com/ja/2019/6/30/debian%E3%81%A6%E3%81%AE%E3%82%B5%E3%83%BC%E3%83%92%E3%82%B9%E3%81%AE%E5%81%9C%E6%AD%A2%E9%96%8B%E5%A7%8B%E5%86%8D%E8%B5%B7%E5%8B%95/
