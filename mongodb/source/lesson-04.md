# shell: query

## データ検索

findでデータを検索します。　

```
> db.foods.find({})
```

フィールドを指定できます。

```
> db.foods.find({name: 'sushi'})
```

一意の `_id` で検索することもできます。insert時に指定していなければ、ObjectId型の識別子が設定されています。

```
> db.foods.find({_id: ObjectId('58d7d09bed8eaf7f564b144b')})
```

結果が一つの場合はfindOneが便利です。

```
> db.foods.findOne({name: 'sushi'})
```

findOneは初めに見つけた一つだけを返します。

詳細は下記を参照。

- https://docs.mongodb.com/manual/reference/method/db.collection.find/
- https://docs.mongodb.com/manual/reference/method/db.collection.findOne/

## 複雑な検索

不等式を使えます。

```
> db.foods.find({rate: {$gt: 2}})
```

フィールド名にdot notationが使えます。

```
> db.foods.find({'likes.person': 'john'})
```

詳細は下記を参照。

- https://docs.mongodb.com/manual/tutorial/query-documents/
- https://docs.mongodb.com/manual/reference/operator/query/

## カーソル

検索結果に対する処理もできます。例えば、ソート。

```
> db.foods.find({}).sort({createdAt: 1})
```

詳細は下記を参照。

- https://docs.mongodb.com/manual/reference/method/js-cursor/

## 課題

1. 上記の動作を確認する
2. 色々な方法でドキュメントを検索する
3. ドキュメントをさらに登録して検索する
