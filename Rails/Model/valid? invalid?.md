# valid?とinvalid?

## valid?
バリデーションが実行された結果
エラーが無い場合`true`を返し，エラーが発生した場合`false`を返す

``` micropost.rb
class Micropost < ApplicationRecord
  validates :content, presence: true, length: { maximum: 140 }
end
```

``` micropost_test.rb
  test "content should be at most 140 characters" do
    @micropost.content = "a" * 141 #=> false
    assert_not @micropost.valid?
  end
```

## invalid?
`valid?`とは逆の結果を返す
エラーが発生した場合`true`，エラーが無い場合`false`を返す

## 参考
[Active Record バリデーション - Rails ガイド] (https://railsguides.jp/active_record_validations.html#valid-questionmark%E3%81%A8invalid-questionmark)

[13.1.2 Micropostのバリデーション - Railsチュートリアル] (https://railstutorial.jp/chapters/user_microposts?version=5.1#sec-micropost_validations)
