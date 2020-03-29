# Slim導入方法

## 必要なライブラリ

* slim-rails
* html2slim (erbからslimへ変換)

## インストール

``` Gemfile
gem 'slim-rails'
gem 'html2slim'
```

` bundle install `

## erbからslimへの変換

``` bundle exec erb2slim app/view/layouts/ --delete ```
