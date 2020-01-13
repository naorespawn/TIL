## Mass Assignment
複数のカラムをまとめて指定すること

``` user_controller.rb
user = User.new(email: "hoge@email.com", password: "hoge")
```

## Strong Parameters
許可されたカラムのみ使えるようにすること

* `require` 必須とする属性 なければ例外となる
* `permit` 許可する属性 全て揃ってなくとも良い

``` user_controller.rb
private
  def user_params
    params.require(:user).permit(:email, :password)
  end
```

## リンク
[Strong Parameters - Railsガイド] (https://railsguides.jp/action_controller_overview.html#strong-parameters)
[GitHub、Mass Assignment利用の脆弱性を突かれる] (https://www.infoq.com/jp/news/2012/03/GitHub-Compromised/)
