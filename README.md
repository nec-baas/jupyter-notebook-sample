Jupyter Notebook 連携サンプル
=============================

Jupyter Notebook からNECモバイルバックエンド基盤(以下BaaS)のJSONオブジェクトストレージのデータを取得するサンプルです。
Python コードから REST API 経由でデータを取得するため、直接MongoDBへアクセスする必要がありません。
サンプルは Python3 で動作確認を行っています。

事前準備
--------

### 1. 既に以下を導入済みのものとして説明を記載します。

* BaaS サーバ
* Jupyter Notebook

### 2. 必要な Python パッケージのインストール

モバイルバックエンド基盤 Python SDK と、必要なライブラリ(pandas, matplotlib)
を pip でインストールします。

    $ pip install necbaas pandas matplotlib

### 3. サンプルデータ登録

サンプルで利用するデータを以下の手順で登録してください。
    
※本データは気象庁提供の[気象データ](https://www.data.jma.go.jp/obd/stats/etrn/index.php)を利用しています。    
    
#### 3-1) デベロッパコンソールよりオブジェクトバケットを作成

* バケット名： "Sample_WeatherData"
* バケットACL： デフォルトのまま
* コンテンツACL： 以下の通り

       {
         "r": ["g:anonymous"],
         "w": ["g:authenticated"],
         "c": [],
         "u": [],
         "d": []
       }

#### 3-2) デベロッパコンソールよりデータインポート

バケット一覧から、作成したバケットの「データ」を選択し、
以下のファイルをアップロードしてください。

* data/Sample_WeatherData.json

実行手順
--------

サンプルの Notebook (*.ipynb) を Jupyter Notebok にアップロードし、サンプル内の記載に従い実行してください。


関連リンク
----------

* NECモバイルバックエンド基盤: https://nec-baas.github.io
* Jupyter Notebook： http://jupyter.org/
