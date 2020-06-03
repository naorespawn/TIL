# Dockerfile記法

[Dockerfile リファレンス — Docker-docs-ja 17.06 ドキュメント](http://docs.docker.jp/engine/reference/builder.html)

## 基礎

* `\`でエスケープ
* `#`でコメント

## FROM

* DockerHubに挙げられているイメージから取得
* 正しい Dockerfile は FROM 命令から始める
* 基本的に公式のイメージを使用する

```Dockerfile
FROM <image> [AS <name>]
FROM <image>[:<tag>] [AS <name>]
FROM <image>[@<digest>] [AS <name>]
```

## RUN

* コマンドを実行する
* 何度でも使用できる
* `\`を用いて複数行に記述できる

```Dockerfile
RUN <command>
RUN ["executable", "param1", "param2"] 

RUN apt-get update \
    apt-get install
```

## CMD, ENTRYPOINT

* コンテナ起動時にコマンドを実行する
* 1つのDockerfileにつき1回ずつまで(複数ある場合は最後の記述のみ)
* `CMD`, `ENTRYPOINT` いずれか1つは必要
* `ENTRYPOINT`, `CMD`の順番で実行される

```Dockerfile
CMD ["executable","param1","param2"] #exec形式
CMD command param1 param2            #shell形式

ENTRYPOINT ["executable", "param1", "param2"] #exec形式
ENTRYPOINT command param1 param2              #shell形式
```

## ADD, COPY

* `<src>`で指定したファイル,ディレクトリを`<dest>`パスへコピーする
* ほとんど同じ機能を持つ
* `COPY`を基本的に使用する
* `ADD`は圧縮ファイルを扱う際に使用する
* [Best practices for writing Dockerfiles | Docker Documentation](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#add-or-copy)

```Dockerfile
ADD hom* /mydir/        # "hom" で始まる全てのファイルを追加
ADD hom?.txt /mydir/    # ? は１文字だけ一致します。例： "home.txt"

COPY hom* /mydir/        # "hom" で始まる全てのファイルを追加
COPY hom?.txt /mydir/    # ? は１文字だけ一致します。例： "home.txt"
```
## EXPOSE

* 公開ポートを指定する

```Dockerfile
EXPOSE <port> [<port>/<protocol>...]
```

## ENV 

* 環境変数を設定する

```Dockerfile
ENV <key> <value>
ENV <key>=<value>
```

## WORKDIR

* `RUN`, `CMD`, `ENTRYPOINT`などのWorkingDirectoryを指定

```Dockerfile
ENV DIRPATH /usr/src
WORKDIR $DIREPATH
```

## VOLUME

* コンテナに依存しない外部記憶領域をマウントする
* JSON形式(`""`ダブルクォートを使用)
* コンテナに依存しないストレージ
* `-volumes-from <コンテナ名>`は指定コンテナの設定を用いてマウントする

```Dockerfile
VOLUME ["/data"]
```

### ボリュームコンテナ(Data Volume Container)

* `-volumes-from`専用のコンテナ
* 軽いイメージにマウントの記述をまとめておく
* `-v`の記述を減らすテクニック
