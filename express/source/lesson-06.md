# middleware

middlewareを使うと様々な機能を拡張することができます。
既に使った、body-parserやexpress.staticもmiddlewareです。

middlewareは基本的に3引数の関数であり、`app.use`で読み込みます。

簡単な例として、アクセスしたURLを記録するmiddlewareを追加します。

```
app.use((req, res, next) => {
  console.log(new Date(), req.url);
  next();
});
```

ここで、第3引数のnext()を呼ぶことが重要で、
そうすることでリクエストの処理が進みます。
逆に、middlewareでレスポンスを返してしまう場合は、
next()を呼ばずに処理を止めることができます。

また、middlewareは個別の`app.get()`にも設定できます。

## 課題

- 上記のmiddlewareの動作を確認する
- `/restricted`にアクセスした場合に、エラーを返すmiddlewareを作る
- urlを内部的に書き換えるmiddlewareを作る

## 参考情報

- http://expressjs.com/en/4x/api.html#app.use
- http://expressjs.com/en/guide/using-middleware.html
