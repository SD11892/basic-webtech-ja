# GET

まずは、最低限のトップページを返すサーバを作ります。

`app.js`を次のようにしてください。

```
const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.send('it works!');
});

app.listen(process.env.PORT || 3000);
```

これを起動するには次のようにします。

```
$ node app.js
```

慣例としては、npm scriptsにエントリーを追加します。
(そのまま、コピペはできないので注意)

```
{
  "scripts": {
    "start": "node app.js"
  }
}
```

このようにすると、

```
$ npm start
```

で起動できます。

http://localhost:3000/ にアクセスしてページが表示されることを確認しましょう。

## APIとしてJSONを返したい場合

Webアプリにおいては、サーバからJSONでデータを返すことがよくあります。

`app.js`に下記を追加しましょう。

```
app.get('/api/hello', (req, res) => {
  res.json({ hello: 'world' });
});
```

http://localhost:3000/api/hello にアクセスして確認しましょう。

## 課題

- 新しいURLでテキストを返す
- 新しいURLでJSONを返す

## 参考情報

- http://expressjs.com/en/4x/api.html#app.get.method
- http://expressjs.com/en/4x/api.html#res.send
- http://expressjs.com/en/4x/api.html#res.json
