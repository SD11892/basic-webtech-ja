# shell: insert

## mongo serverの起動

OSによってはすでに起動している場合がありますが、そうでない場合は
新しいターミナルでmongodを起動します。

```
$ mongod
```

場合によっては事前に適切な権限で `/data/db` を作成しておく必要があります。

## mongo shellの起動

db名を指定して起動します。

```
$ mongo test
```

mongo shellのプロンプトは `>` で表現します。

```
> db.getName()
```

でデータベースの名前が表示されます。

## insertOne

insertでコレクションにドキュメントを登録します。

```
> db.foods.insertOne({"name": "sushi", "rate": 5})
```

ドキュメントの構造は自由です。　

```
> db.foods.insertOne({"name": "yakiniku", "rate": 3, "count": 1})
```

複雑な構造のドキュメントも可能です。

```
> db.foods.insertOne({"name": "sukiyaki", "likes": [{"person": "john"}, {"person": "mike"}]})
```

## insertMany

配列でドキュメントを渡してまとめて追加します。

- https://docs.mongodb.com/manual/reference/method/db.collection.insertMany

## BSON

ドキュメントはバイナリを扱えるJSON拡張であるBSONを使います。

- https://docs.mongodb.com/manual/reference/bson-types/
- https://docs.mongodb.com/manual/reference/mongodb-extended-json/

例えばDateが使えます。

keyのダブルクオートは省略可能です。またシングルクオートも使えます。

```
> db.foods.insertOne({name: 'karaage', createdAt: new Date()})
```

`_id`はprimary keyとして予約されています。指定しないと自動で割り振られます。

また、keyには `.` は含められません。nullもダメです。`$`で開始できません。

ドキュメントのサイズは最大16MBです。

## 課題

1. 上記の動作を確認する
2. 色々なドキュメントを登録する
3. 別のコレクションにドキュメントを登録する
