# アセットパイプラインとは
JavaScriptやCSSなどのアセットを最小化し連結するためのフレームワーク

## 処理内容
1. 高級言語のコンパイル
  SCSS, Slim, ERBなどをコンパイルしJavaScriptやCSSファイルとして扱う
2. アセットの連結
  複数のアセットをひとつのファイルへ連結する
3. アセットの最小化
  スペース 改行 コメントを削除し通信量を削減
4. ダイジェストの付与
  内容からハッシュを作成しファイル名末尾に付与 コードの変更とともにファイル名も変わる

## 環境による挙動の違い
* Development環境
  コンパイルとダイジェストの付与が実行される
* Production環境
  アセットパイプライン全ての処理が実行される

## どうやって連結するか
### マニュフェストファイル
どのように連結して出力するかを記述するファイル

`app/assets/application.css`

`app/assets/application.js`

デフォルトではCSS, Javascriptでそれぞれ1つだが，2つ以上設定できる

### 記述法
CSS,Javascriptの場合

```
//= require rails-ujs # 指定したファイルを読み込む
//= require_tree .    # 指定したディレクトリ以下の全ファイルを読み込む
```

Sassの場合

```
@import "bootstrap";
```

# リンク
[アセットパイプライン - Railsガイド](https://railsguides.jp/asset_pipeline.html)
