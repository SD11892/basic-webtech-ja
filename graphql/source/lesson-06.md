# Schemaの例その2

SchemaにはQueryの他にMutationもあります。

## MutationのSchema

MutationのSchemaもQueryと同じです。

```
type Mutation {
  addItem(title: String): Boolean
}
```

ミューテーションの戻り値はオブジェクトを返しても構いません。
実はクエリでデータの操作をすることもできてしまいます。
複雑なデータを引数で渡す場合はinput typeを使うことができます。

## コメント

コメントは`#`で書けます。

```
type Item {
  # title for this item
  title: String
}
```

コメントは、消えるものではなく、GraphQLのドキュメントになるので
しっかり書くとよいでしょう。

## 課題

1. 何か想像でミューテーションのSchemaを書いてみる

## 参考情報

- http://graphql.org/learn/schema/
