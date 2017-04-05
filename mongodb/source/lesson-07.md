# node.js driver

これまではmongo shellを使ってきましたが、
プログラムから使う場合はnode.js driverを使います。

## 例

下記の内容でmongotest.jsというファイルを作成します。

```
const MongoClient = require('mongodb').MongoClient;

MongoClient.connect('mongodb://localhost:27017/test', (err, db) => {
  if (err) return console.error(err);
  const collection = db.collection('foods');
  collection.find({}).toArray((err2, docs) => {
    console.log(docs);
    db.close();
  });
});
```

実行します。

```
$ node mongotest.js
```

結果が表示されるはずです。

非同期処理で記述する必要があるので注意が必要です。
promiseやes2017のasync/awaitを使うこともできます。

詳細は下記を参照。

- https://mongodb.github.io/node-mongodb-native/
- https://mongodb.github.io/node-mongodb-native/2.2/api/

## 課題

1. 上記の動作を確認する
2. insertOneを使う
3. findOneを使う
4. updateOneを使う
5. aggregateを使う
