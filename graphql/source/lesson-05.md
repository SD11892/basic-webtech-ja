# Schemaの例

GraphiQLが便利に使えるのはJSONデータのSchemaが定義されているからです。

## QueryのSchema

### Object types and built-in scalar types

オブジェクトのタイプを定義します。

```
type Character {
  name: String!
  appearsIn: [Episode]!
}
```

ここで、Stringはスカラータイプで、Episodeは別に定義されるオブジェクトタイプです。

`!`は必須フィールドであること示します。(正確にはnon-null)

あらかじめ用意されているスカラータイプは下記です。

- Int: 符号付き32ビット整数
- Float: 符号付きdoubleサイズの浮動小数点数
- String: UTF-8文字列
- Boolean: 真偽値(`true` / `false`)
- ID: 内部的には文字列だが、人間が読めることを想定しない

スカラータイプを独自に定義することもできます。

```
scalar Date
```

### Arguments and enumeration types

全てのフィールドには引数を設定できます。

```
type Starship {
  id: ID!
  name: String!
  length(unit: LengthUnit = METER): Float
}
```

この例では、lengthフィールドにunitという引数がつけられ、それはLengthUnitという方を持ち、そのデフォルト値はMETERになります。

LengthUnitはenumタイプで例えば下記のように定義されます。

```
enum LengthUnit {
  METER
  FOOT
}
```

### その他

今回は詳しくは取り扱いませんが、`interface`や`union`や`input`という構文も用意されています。

## Queryの定義

Queryという特殊なタイプをルートに定義します。

```
type Query {
  hero(episode: Episode): Character
  droid(id: ID!): Droid
}
```

以前はこれに加えて、

```
schema {
  query: Query
}
```

が必要でしたが、今は不要になりました。(要出典)

## 課題

1. 何か想像でクエリのSchemaを書いてみる

## 参考情報

- http://graphql.org/learn/schema/
