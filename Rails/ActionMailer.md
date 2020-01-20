# ActionMailer

Railsが提供するメールを送るための仕組み

## メイラーの生成

```
rails g mailer UserMailer
```

## メイラーの編集

Railsのコントローラーに似ている

`app/mailer/user_mailer`

```
class UserMailer < ApplicationMailer
  default from: 'mailer@example.com'
 
  def welcome_email
    @user = params[:user]
    @url  = 'http://example.com/login'
    mail(to: @user.email, subject: '私の素敵なサイトへようこそ')
  end
end

```
ビューで使用するためにインスタンス変数を定義

`mail`メソッドが実際のメールメッセージとなる

## メイラービューの作成

`app/views/user_mailer`に作成する

HTML形式, text形式の2パターンを用意

## メイラーの呼び出し

新規ユーザー登録が完了するとメイラーを呼び出す

``` users_controller.rb
class UsersController < ApplicationController
  def create
    @user = User.new(params[:user])
    if @user.save
      # 保存後にUserMailerを使ってwelcomeメールを送信
      UserMailer.with(user: @user).welcome_email.deliver_later
      redirect_to(@user, notice: 'ユーザーが正常に作成されました。')
    end
  end
end
```

## リンク
* [Action Mailer の基礎 - Railsガイド](https://railsguides.jp/action_mailer_basics.html)
