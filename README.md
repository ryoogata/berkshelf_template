template berkshelf
=================
template を構築する berkshelf

Requirements
------------

#### mandatory cookbooks
必須 cookbook は下記の通り

- `java`
- `wso2_emm`

#### optional cookbooks
環境によって必要な cookbook は下記の通り

- Database に MySQL を利用する場合   
  - `mysql`
    - バージョンを `5.6.1` に指定   
  - `mysql_connector`
    - MySQL Java connector をインストールするのに必要
  - `database`
    - Database を作成するのに必要
    
- サーバを AWS 上に構築する場合
  - `awstool`
  - `aws`
  - `ohai`
  - `ohai-custom`

  
Attributes
----------

#### mysql

Key|Type|Description|Default
---|---|---|---
['mysql']['version']||バージョンの指定|5.6
['mysql']['server_root_password']||root のパスワード|secretpassword



run_list
-----

#### 1. ( mandatory ) recipe[java::default]
Oracle Java をインストール

#### 2. recipe[mysql::server]
MySQL Server をインストール


License and Authors
-------------------
* Author:: Ryo Ogata ryo.ogata@gmail.com