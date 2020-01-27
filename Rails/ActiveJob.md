# ActiveJob
バックグランドで非同期処理を行うためのフレームワーク

## Redisのインストール

Sidekiqではキーバリュー型のRedisを使用する

```
$ brew install redis
$ redis-server
```

## Sidekiqのインストール

`Gemfile`

``` Gemfile
gem 'sidekiq'
```

```
$ bundle install
$ bundel exec sidekiq
```

`config/enviroments/development.rb`

``` development.rb
  # Use an evented file watcher to asynchronously detect changes in source code,
  # routes, locales, etc. This feature depends on the listen gem.

  config.active_job.queue_adapter = :sidekiq
```
