# ActiveStorage

Rails5.2からRailsに同梱

クラウドストレージサービスへファイルをアップロードし，データベース上でActiveRecordモデルへ紐づける

## ActiveStorageの準備

`rails active_storage:install`を実行しマイグレーションファイルを作成

`rails migrate` DBへ反映

## 2つのDB

`ActiveStorage::Blob`

添付ファイルに対応するモデル　ファイルをDB外で管理することを前提にしている

`ActiveStorage::Attachment` 

`Blob`と他のモデルを関連付ける中間テーブル

## ファイル管理設定

`/config/environments/development.rb`

``` /config/environments/development.rb
  # Store uploaded files on the local file system (see config/storage.yml for options)
  config.active_storage.service = :local
```

初期設定は`:local`となっている

`config/storage.yml`

``` config/storage.yml
local:
  service: Disk
  root: <%= Rails.root.join("storage") %>
```
