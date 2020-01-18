# form_with
Rails5.1から導入されたヘルパー

`form_for` `form_tag`の2つのメソッドを統合された

## 特徴

* `:model`でモデルを指定する
* デフォルトでAjaxを使用する
* Rails5.1では`class, id`が自動付与されない
* Rails5.2以降ではされる


## オプション

| オプション | 説明 |
| :--- | :---|
| `:model` | どのモデルに基づいて作るか|
| `:local` | `true`でAjaxを解除 |
| `:url` | フォームの転送先を指定 |
| `:id, :class, :data` | HTML属性の指定 |
| `:method` | HTTPリクエストの指定 |

## リンク
* [form_withについて解説 | WEBCAMP NAVI ](https://web-camp.io/magazine/archives/17665)
* [Ruby on Rails 5.1 リリースノート - Railsガイド]( https://railsguides.jp/5_1_release_notes.html#form-for%E3%81%A8form-tag%E3%81%AEform-with%E3%81%B8%E3%81%AE%E7%B5%B1%E5%90%88)
