# 基礎コマンド

## イメージ
```bash
# イメージ取得
$ docker image pull IMAGE_ID
# イメージ作成 (Dockerfileから)
$ docker build
# イメージ一覧
$ docker images -a
# イメージ削除
$ docker rmi
# コンテナからイメージを作成
$ docker commit
```

## コンテナ
```bash
# コンテナの作成
$ docker create --name CONTAINER_NAME IMAGE_ID
# コンテナの一覧
$ docker ps
# コンテナの削除
$ docker rm CONTAINER_ID
# コンテナの実行
$ docker start CONTAINER_ID
# コンテナの停止
$ docker stop CONTAINER_ID
```

## docker-compose
```bash
# イメージの構築
$ docker-compose build --no-cache
# コンテナの起動
$ docker-compose start
# コンテナを構築し，起動
$ docker-compose up -d
```

## 全削除
``` bash
# 全コンテナ停止
$ docker stop $(docker ps -q)
# 全コンテナ削除
$ docker rm $(docker ps -q -a)
# 全イメージ削除
$ docker rmi $(docker images -q)
```
