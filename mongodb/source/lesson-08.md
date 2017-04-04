# import/export

## データのexport

データをファイルに出力できます。

```
$ mongoexport --db test --collection foods --out foods.json
```

foods.jsonというファイルができているはずです。
このjsonファイルはテキストであり簡単に処理できます。

詳細は下記を参照。

- https://docs.mongodb.com/manual/reference/program/mongoexport/

## データのimport

exportしたファイルを入力できます。

```
$ mongoimport --db test --collection foods --file foods.json
```

これは追加で登録しようとするため、すでに同じドキュメントがあるとエラーになります。

```
$ mongoimport --db test --collection foods --file foods.json --drop
```

これは削除してから登録するため、すでにあるデータは消されます。

詳細は下記を参照。

- https://docs.mongodb.com/manual/reference/program/mongoimport/

## dump/restore

export/importとは別のdump/restoreもあります。
これはバイナリデータを入出力するツールです。

詳細は下記を参照。
- https://docs.mongodb.com/manual/reference/program/mongodump/
- https://docs.mongodb.com/manual/reference/program/mongorestore/

## 課題

1. 上記の動作を確認する
