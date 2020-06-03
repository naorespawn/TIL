# Bundlerとは

Gemの互換性を保ちながらGemの導入, 管理を行う

## 使用方法

1. Bundlerをインストール 
  * `gem install bundler`
2. 使用したいGemをGemfileに記載する
  * source "rubygems"
  * gem "Rails"
3. Gemfileのリストに基づいてGemをインストール
  * `bundle install --path vendor/bundle`
4. BundlerでインストールされたGemを用いて実行
 * `bundle exec rails new --skip-bundle`
 * `bin/rails rails new --skip-bundle`
