# session 

よく使われるmiddlewareの一つにsessionがあります。
これは、サーバサイドで複数のリクエストをまたいでデータを保存する仕組みです。

まずはパッケージをインストールします。

```
$ npm install express-session --save
```

`app.js`に追記します。

```
const session = require('express-session');

app.use(session({
  secret: '64d7ba42b311fb630bbb9a29',
  resave: true,
  saveUninitialized: true,
}));
```

セッションを使う例として、カウンターを作ります。

```
app.get('/counter', (req, res) => {
  req.session.counter = (req.session.counter || 0) + 1;
  res.json({ counter: req.session.counter });
});
```

`http://localhost:3000/counter`にアクセスして動作を確認しましょう。
プライベートブラウジングなどを使うとよいでしょう。

この状態ではセッションのデータはメモリ上に保存されているだけなので、
サーバを再起動するとリセットされてしまいます。
本番環境では、何かしらの[session store](https://github.com/expressjs/session#compatible-session-stores)を使うことになります。

## 課題

- セッションを使った機能を作る

## 参考情報

- https://github.com/expressjs/session
