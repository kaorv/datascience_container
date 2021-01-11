# datascience_container

### 前提条件
docker,docker-compose がinstallされている.


### 起動手順
1. datascience_container-main/(zip解凍した後のフォルダ直下)に移動して,下記コマンドを実行する.
```
docker-compose up --build -d
```

2. 1のコマンドが実行完了し,以下コマンドを打ち,stateが Up になっていればコンテナは立ち上がっている.
```
docker-compose ps
```

3. 立ち上がった場合,[http://localhost:8888](http://localhost:8888)にアクセスする.

4. アクセスできたらsrc/test.ipynbの1セル目を実行して,importできたらコンテナ作成成功となる.

5. 追加でライブラリをinstallする時は,src/Dockerfileの初期ライブラリinstallのところに真似して追加する.