# ReactTutorial

## 環境構築
```bash
# node.jsをインストール
$ git clone https://github.com/creationix/nvm.git ~/.nvm
$ source ~/.nvm/nvm.sh
$ nvm ls-remote
# 最新の LTS 版をインストール
$ nvm install v8.9.4

# yarnをインストール
$ brew install yarn

# アプリケーションを作成
$ npx create-react-app my-app
```

## コンポーネント

```js
class App extends React.Component {
  render() {
    return <h1>Hello!</h1>;
  }
}
```
コンポーネントとはViewの一部分を切り出したもの

`React.Component`を継承したクラスとして作成し，`Render`メソッドでJSXを返す　頭文字は大文字

### 関数コンポーネント

`render`メソッドだけを有して自身の`state`を持たないコンポーネント

```js
function Square(props) {
  return (
    <button className="square" onClick={props.onClick}>
      //this.props ではなく props
      {props.value}
    </button>
  );
}
```

## PropsとStats

Properties(特性,特質)とStat(状態)

Propsは親コンポーネントから指定される固定データ

Statはコンポーネント自身が所持する可変データ

### Props

JSXに書かれている属性，子要素を単一のオブジェクトとして扱う

そのオブジェクトのことを`Props`と呼ぶ

## JSX

Javascriptの式を中括弧`{}`に囲んで記入する記法

### 子要素

タグが空の場合`/>`でタグを閉じれる

` const element = <img src={user.avatarUrl} />;　`

## 命名規則

イベントを表す `props` には `on[Event]` という名前

イベントを処理するメソッドには `handle[Event]` という名前を付けるのが慣習
