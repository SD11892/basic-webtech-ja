# shell: update

## データ更新

検索した結果について、update operatorでデータを更新できます。

```
> db.foods.updateOne({_id: ObjectId('58d7d09bed8eaf7f564b144b')}, {$set: {visited: true}})
```

複数のデータを更新することもできます。

```
> db.foods.updateMany({}, {$inc: {counter: 1}})
```

詳細は下記を参照。

- https://docs.mongodb.com/manual/reference/operator/update/

## データ削除

- https://docs.mongodb.com/manual/reference/method/db.collection.remove/


## 検索と更新を同時に行う

- https://docs.mongodb.com/manual/reference/method/db.collection.findAndModify/

## 課題

1. 上記の動作を確認する
2. 色々な方法でドキュメントを更新する
3. removeやfindAndModifyを試す
