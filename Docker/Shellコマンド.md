# 基礎コマンド

## イメージ
```bash
# イメージの取得
$ docker image pull ruby:latest
# イメージの確認
$ docker image ls
# イメージの削除
$ docker rmi IMAGE_ID
```

## コンテナ
```bash
# コンテナの作成
$ docker container create --name ruby IMAGE_ID
# コンテナの確認
$ docker container ls -a
# コンテナの削除
$ docker container rm CONTAINER_ID
# コンテナの実行
$ docker container start CONTAINER_ID
# コンテナの停止
$ docker container stop CONTAINER_ID
```

## docker-compose
```bash
# イメージの構築
$ docker-compose build
# コンテナの構築, 起動
$ docker-compose up
# コンテナの起動
$ docker-compose start
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
