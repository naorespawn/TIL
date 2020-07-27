# ENTRYPOINTとCMDの違い

## CMD
* `$ docker run ~ `のデフォルトの引数

例として`CMD ["/bin/bash"] `ならば

```bash
$ docker run -it web
$ docker run -it web /bin/bash
```
上記コマンドは同義である

* 引数を指定することでCMD命令を上書きできる

` $ docker run -it web /bin/zsh` 

## ENTRYPOINT

* `$ docker run`時に実行されるコマンド
* `$ docker run`の引数で上書き出来ない

## 併用

```
ENTRYPOINT ["ping"]
CMD ["127.0.0.1", "-c", "50"]
```

* 併用すると`ENTRYPOINT`の引数として`CMD`が利用される
* 結果として`ping 127.0.0.1 -c 50`が実行される

``` 
$ docker run -it web localhost
$ ping localhost
```
* 結果として`$ docker run`の引数が`ENTRYPOINT`コマンドの引数となる
