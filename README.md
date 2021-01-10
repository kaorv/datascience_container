# datascience_container

### 前提条件
docker,docker-compose がinstallされている.


###　起動手順
1. src/に移動して,下記コマンドを実行する.
```
docker-compose up --build -d
```

2. [http://localhost:8888](http://localhost:8888)にアクセスする.


3. アクセスできたらsrc/test.ipynbの1セル目を実行して,importできたらコンテナ作成成功となる.


4. 追加でライブラリをinstallする時は,src/Dockerfileの初期ライブラリinstallのところに真似して追加する.