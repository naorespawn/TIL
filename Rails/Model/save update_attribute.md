## オブジェクトの更新
### save

``` save.rb
user = User.new(name: "new", email: "hoge@example.com")
user.save
```
作成したオブジェクトを保存する
検証に失敗すると`false`を返す

### update_attributes

``` update_attributes.rb
user.update_attributes(name: "qita", email: "foo@bar.com")
```

既にあるオブジェクトを更新する
検証に失敗すると`false`を返す

### update_attribute

``` update_attribute.rb
user.update_attribute(name: "qiita")
```

特定の要素のみ更新し，検証を回避する

## 参考
[第6章 ユーザーのモデルを作成する - Railsチュートリアル](https://railstutorial.jp/chapters/modeling_users?version=4.2#sec-updating_user_objects)
