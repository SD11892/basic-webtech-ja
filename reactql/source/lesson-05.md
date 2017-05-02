# GraphiQL

ReactQLで作成したプロジェクトはデフォルトのGraphQLサーバに接続するようになっています。
GraphiQLでスキーマ等を確認できます。

## エンドポイント

```
$ cat config/project.js 
/* eslint-disable import/prefer-default-export */

export const APOLLO = {
  uri: 'https://api.graph.cool/simple/v1/cinomw2r1018601o42x5z69uc',
};

export const BUNDLE_ANALYZER = {
  openAnalyzer: false,
};
```

この `uri` がGraphQLのエンドポイントです。

## GraphiQL

GrahphiQLのURLはGraphqlのエンドポイントに `/graphiql` をつけたものになります。

## 課題

1. GraphiQLでドキュメントを見る
2. queryやmutationを試す
