# GraphQLとは

WebAPIの規格 クエリ言語とスキーマ言語からなる

## クエリ言語

GraphQLのリクエストのための言語

QueryLanguage: 問い合わせ言語

* データ取得: `query`
* データ更新: `mutation`
* サーバからのイベント通知: `subscription`

## スキーマ言語

GraphQLの仕様を記述するための言語

Schema: データベースの構造

リクエストされたクエリはスキーマによって処理されレスポンスを生成する

## 例

- スキーマ

```schema.rb
type Query {
  currentUser: User!
}

type User {
  id: ID!
  name: String!
}
```

`user!`は`null`を許容しない

- クエリ
```query.rb
query GetCurrentUser {
  currentUser {
    id
    name
  }
}
```

- レスポンス
```response.json
{
  "data": {
    "currentUser": {
      "id": "dXNlci80Mgo=",
      "name": "foo",
    }
  }
}
```
# スキーマ言語のコンポーネント

* Type
* Field
* Interface
* Union
* Scalar
* Enum
* Directive
* Description

# クエリ言語のコンポーネント

* Query
* Mutation
* Variables
* Fragment


