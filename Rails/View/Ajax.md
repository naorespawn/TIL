# Ajaxとは

`Asynchronous Javascript And XML`の略

Webブラウザ上で非同期通信を行い，再読み込みなしにページの更新を行うJavaScriptのプログラミング手法


## DOM

Document Object Model

HTMLをJavascriptなどのプログラムから利用する仕組み

## イベントハンドラによる実装

### イベントハンドラとは

特定の動作がなされたときに呼び出される処理

`mouseover`, `click`, `keydown`など

### Ajaxリクエストを発生させる

`remote: true`オプションを`link_to`メソッドに加える

``` index.html.slim
link_to '削除', task, method: :delete, remote: true, class: 'btn btn-danger delete'
```

`ajax:success`というイベントが発行される

### 成功レスポンスを返す

``` tasks_controller.rb
def destroy
  @task.destroyn
  head :no_content
end
```

`204 No Content`のHTTPレスポンスを返す

### イベントハンドラを実行

``` tasks.js
document.addEventListener('turbolinks:load', function () {
  document.querySelectorAll('.delete').forEach(function (a) {
    a.addEventListener('ajax:success', function () {
      var td = a.parentNode;
      var tr = td.parentNode;
      tr.style.display = 'none';
    });
  });
});
```

* `addEventListener` ページ読み込みが完了したタイミング
* `querySelectorAll('.delete')` 削除リンクの要素群
* 削除リンク`a`の親要素`td`の親要素`tr`を`style.display`で非表示


## SJRによる実装

Server-generated Javascript Responses

サーバサイドで生成したJavascriptからなるレスポンス

手軽だがJavaScriptがあちこちに散らばり共通化しづらくなる

### DOM要素にid属性を付与

``` index.html.slim
tbody
  - @tasks.each do |task|
    tr id="task-#{task.id}"
```
### レスポンスとしてJavaScriptを返す

``` tasks/destroy.js.erb
document.querySelector("#task-<%= task.id %>").style.display = 'none';
```
