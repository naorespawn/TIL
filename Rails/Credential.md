# Credentialsとは
Rails5.2から追加

Production環境用の秘密情報そのもの
秘密情報の管理方法の2つの意味を持つ

## 特徴

* 開発者が秘密情報を確認 変更を行える
* 開発者同士で共有できる
* リポジトリに秘密情報を格納するのを避ける

## 使用方法

`config/master.key` もしくは 環境変数`RAILS_MASTER_KEY`から
キー情報を取り出し暗号化,復号に使用される

`rails credentials`コマンドから閲覧編集を行う

* `:edit` 編集
* `:show` 閲覧
