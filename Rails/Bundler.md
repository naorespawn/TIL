# Bundler
RubyのGem(パッケージ)管理システム

## インストール
```
$ gem install bundler
$ bundler -v
```

## Gemfile
Bunlder用設定ファイル　インストールするGemを記述する

### 作成
```
$ bundle init
```

### 記載方法

```Gemfile
# gemのインストール元を指定
source "https:rubygems.org"

# Rubyのバージョンを指定
ruby '~> 2.7.1'

# gemの指定
rails '~> 6.0'

# バージョン指定方法
rails '6.0.2'     # バージョン固定
rails '>= 6.0.0'  # 6.0.0以上の最新
rails '~> 6.0.3'  # 6.0.3以上, 6.1.0未満
```

## gemのインストール
```
$ bundle install --path vendor/bundle
```

`--path`でgemのインストール先を指定
プロジェクトごとにgemを管理する

## gemコマンドの実行
```
$ bundle exec rails s
```
`bundle exec`を頭につける
