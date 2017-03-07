# Queryの例

GraphQLでは一つの大きなJSONを部分的に取得する形になります。
その取得範囲を示すものがクエリです。
クエリを書くには、取得するJSONデータの形が事前に分かっている必要があります。

## Queries

本レッスンでは、まずクエリの形がどのようになるのかを学習します。

### Fields

```　
{
  hero {
    name
  }
}
```　

このようなクエリを書くと、例えば、次のようなJSONデータが取得できます。

```
{
  "data": {
    "hero": {
      "name": "R2-D2"
    }
  }
}
```

JSONデータとクエリの表記の対照性について注意しましょう。

仮にheroにfriendsがいるとすると次のようなクエリになるでしょう。

```
{
  hero {
    name
    friends {
      name
    }
  }
}
```

このクエリの結果は例えば次のようなJSONデータになります。

```
{
  "data": {
    "hero": {
      "name": "R2-D2",
      "friends": [{
        "name": "Luke Skywalker"
      }, {
        "name": "Han Solo"
      }, {
        "name": "Leia Organa"
      }]
    }
  }
}
```

### Arguments

引数をつけることも可能です。例えば次のようになります。

```
{
  human(id: "1000") {
    name
    height
  }
}
```

```
{
  "data": {
    "human": {
      "name": "Luke Skywalker",
      "height": 1.72
    }
  }
}
```

上記例では`human`に引数が付いていますが、どこにでもつけることができます。
例えば、`height(unit: FOOT)`としてフィートでの身長データを取得することもできるでしょう。


## Mutations

GraphQLにはデータを取得するためのクエリだけでなく、データを変更するためのミューテーションもあります。その形式はクエリと同じです。

## 参考情報

- http://graphql.org/learn/queries/ 
