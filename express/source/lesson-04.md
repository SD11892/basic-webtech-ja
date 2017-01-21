# POST

JSON APIにおいてはPOSTでクライアントからデータを受け取ることが多いです。

POSTでbodyとしてJSONを受け取るには、body-parserを使います。

```
$ npm install body-parser --save
```

`app.js`に下記を追加します。

```
const bodyParser = require('body-parser');

app.use(bodyParser.json());
```

`require`文はファイル上部にまとめる方がよいです。

続いて、APIの定義を`app.js`に追加します。

```
app.post('/api/hello', (req, res) => {
  const name = req.body.name || 'unknown';
  res.json({ hello: name });
});
```

動作確認には`curl`コマンドを使います。

```
$ curl -H "Content-type: application/json" -X POST -d '{"name":"apple"}'  http://localhost:3000/api/hello
```

もしくは[Postman](https://www.getpostman.com)などのアプリを使いましょう。

## 課題

- nameを変えて呼び出す
- 新たなURLでAPIを作成する

## 参考情報

- https://github.com/expressjs/body-parser
- http://expressjs.com/en/4x/api.html#app.post.method
