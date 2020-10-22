# docker-compose記法

[Compose ファイル・リファレンス — Docker-docs-ja 17.06 ドキュメント](http://docs.docker.jp/compose/compose-file.html#environment)

## version

* メジャーナンバーだけの指定`version: '3'`は`version: '3.0'`と同義となる
* 最新バージョンを使用したい場合は`version: '3.8'`と指定する

## ports

* 公開用ポートを指定
* `"HOST:CONTAINER"`として指定

## volumes

* データ永続化領域
* `volumes`に指定されたデータは，過去に実行したコンテナから新しいコンテナにコピーされる
* 指定したデータが維持される
* ホストとデータ共有するには`host側パス:container側パス`と指定
* 名前付きボリューム`datavolume:/var/lib/mysql`

## stdin_open

* コンテナの標準入力にアタッチ
* `docker run -i`と同義

## tty

* 疑似ターミナル (pseudo-TTY) を割り当てる
* `docker run -t`と同義
