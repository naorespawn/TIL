# find, find_byの違い

## find
主キー`(:id)`に一致するオブジェクトを取り出す

``` ruby:find.rb
user = User.find(id: 1)
# => #<Client id: 1, name: "Qiita">
```

複数の主キーを渡すと，配列で返す

``` ruby:find_array.rb
users = User.find(id: 1, 2)
# => {
# <Client id: 1, name: "Qiita">,
# <Client id: 2, name: "Micheal">
# }
```

## find_by
与えられた条件に一致するオブジェクトを取り出す

``` ruby:find_by.rb
user = User.find_by(name: "Micheal")
# => <Client id: 2, name: "Micheal">
user = User.find_by(id: 1)
# => <Client id: 1, name: "Qiita">
```

## 参考リンク
[Active Record クエリインターフェイス - Rails ガイド] (https://railsguides.jp/active_record_querying.html)
