# 能登半島地震2024における地盤変動ベクトル推定
OpenCVテンプレートマッチングを用いた画像差分ベクトル解析

## 概要
2024年1月に発生した能登半島地震の地震前後の地形陰影図を比較し、地盤変動ベクトルを画像処理により推定します。

## 使用技術
- Python 3.9+
- OpenCV
- NumPy
- Matplotlib
- folium
- geopandas
- shapely
- rasterio
- fiona
- pycrs
- gdal
## 実行方法
-Jupyter Notebook を開いて、セルを順に実行してください。
+Google Colab または Jupyter Notebook で以下のノートブックを実行できます。  
+
### 基本版（template_03c3.ipynb）
+- [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yokayoka/noto-landslide-opencv/blob/main/template_03c3.ipynb)
+
  
### ノイズ低減版（template_05a2.ipynb）
+- [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yokayoka/noto-landslide-opencv/blob/main/template_05a2.ipynb)
+
  
+どちらもセルを上から順に実行してください。必要なサンプル画像はリポジトリ内の `data/` フォルダに格納されています。

## 入力画像

本リポジトリのサンプルスクリプトでは、Notebookの実行のため、輪島市真喜野地区のデータをサンプルとして使用しています。いずれも下記のリンクからダウンロードしてご自分の Google Drive 内の適切なフォルダーに配置してご利用ください。また、ご自分でGIS等を用いて陰影図を作成することも可能です。ご自分で作成する際は、空間参照は (EPSG: 6675)、ピクセルサイズ: 0.5m　を推奨します。元となるDEMは、地震前については[石川県森林管理課のデータ](https://www.geospatial.jp/ckan/dataset/2024-notowest-ground)を、地震後については[林野庁](https://www.geospatial.jp/ckan/dataset/rinya-dem-noto2024)が[G空間情報センター](https://front.geospatial.jp/)から公開したものを利用することが出来ます。

- [地震前の陰影図](https://drive.google.com/file/d/1CtKBV6IndaHTEspJjDKagERQx7KLTYeR/view?usp=drive_link)：`makino/bf_shade/bf_shade_ED673_881.tif`  
  [石川県森林管理課のDEM](https://www.geospatial.jp/ckan/dataset/2024-notowest-ground) より作成

- [地震後の陰影図](https://drive.google.com/file/d/1TujWEA7cf91GJQs2PYuu25aXKXInqHe5/view?usp=drive_link)：`makino/af_shade/af_shade_ED673_881.tif`  
  北陸地方整備局より提供（同等の陰影図は [林野庁の発災後DEM](https://www.geospatial.jp/ckan/dataset/rinya-dem-noto2024) より作成）

- 「ED」＋3桁の数字（例：`ED673_881`）は、平面直角座標系7系における国土基本図の図郭名に対応しています。


### 注意点
- 地震前後の陰影図は、**同一範囲・同一サイズ**の画像を使用してください。
- DEMの元データ（点群密度・取得手法）に違いがあると、マッチング精度が低下する可能性があります。

## ライセンス
本リポジトリのコードおよびドキュメントは、[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) のもとで提供されています。

## 特許に関する注意

本リポジトリで公開している技術や解析手法の一部は、国際航業株式会社が保有する以下の特許技術に類似する可能性があります：

- [地形画像を用いた地形変化の解析方法及びそのプログラム（特許公開番号 JP2010030481）](https://jglobal.jst.go.jp/detail?JGLOBAL_ID=201003048172036189)

これらの技術に関連する特許権の権利範囲に該当するかどうかは、最終的には利用者の責任においてご判断ください。特に商用利用を検討される場合は、必ず事前に法的確認を行ってください。

本リポジトリの管理者は、当該特許に関わる一切の知的財産権上の問題について責任を負いません。
