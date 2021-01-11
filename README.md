# datascience_container
これは,jupyterのimage(ここでは,jupyter/datascience-notebookを用いている.)を用いた,簡単なdockerコンテナである.

## 前提条件
docker,docker-compose がinstallされている.


## 起動手順
1. zipファイルをダウンロードし,Desktop上で解凍する.

2. datascience_container-main/(zip解凍した後のフォルダ直下)に移動して,下記コマンドを実行する.(初回,imageを消している場合は30分程度かかる.)
```
docker-compose up --build -d
```

3. 1のコマンドが実行完了し,以下コマンドを打ち,stateが Up になっていればコンテナは立ち上がっている.
```
docker-compose ps
```

4. 立ち上がった場合,[http://localhost:8888](http://localhost:8888)にアクセスする.

5. あとは,jupyternotebookが使える.(このコンテナはJuliaやRも使える.)

## 使い方
### ライブラリ追加install方法 
1. 追加でライブラリをinstallする時は,/datascience_container-main/src/Dockerfileの"初期ライブラリinstall"のところに真似して追加する.

2. セル上,またはTerminalでpipを用いてinstallする.

### localで作成したファイルを用いたい場合
1. localで作成したファイルを用いたい場合は,/datascience_container-main/src/の中にファイルを入れるとリアルタイムでコンテナにも反映される.

### コンテナで書いたファイルを取り出したい
1. /Desktop/datascience_container-main/src/に反映されているものを取り出せば良い.コンテナを閉じても,コンテナの中で作成したファイルは./src/内に残り続ける.


## 使い終わったら
1. 割と容量が大きいものでありportも占有してしまうので,使い終わったらコンテナは捨てる方が良い.
```
docker-compose down
```

2. 自身のPCに容量が少ない場合は,imageも消しておいた方が良い.(ただ,毎回imageから作り直すと時間がかかるので,できればそのままの方が良い.)
```
docker rmi datascience_container-main_notebook jupyter/datascience-notebook -f
```

3. 次回起動時は,起動手順の2から行う.

## 備考
1. src/に入れたファイルが反映されない場合は,docker-compose.ymlの中にあるvolumesの":"より左側がlocalのsrcフォルダの場所を示しているので,そこのpathを変えると良い.

2. 極力楽をして無駄を省きたい場合は,Dockerfile2行目で用いているimageを"jupyter/minimal-notebook"などの他のimageに変更しても良い.[jupyternotebookのimage一覧](https://qiita.com/kshigeru/items/ea174d6bcacc474f2a51)