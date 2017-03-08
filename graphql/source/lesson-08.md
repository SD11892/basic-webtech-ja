# クライアントのコード例

publicフォルダを作ります。

```
$ mkdir public
```

server.jsに下記を追記します。

```
app.use('/', express.static(require('path').join(__dirname, 'public')));
```

app.listenの前に書きましょう。

public/index.htmlを次のように作成します。

```
<html>
  <head>
    <script src="https://wzrd.in/standalone/apollo-client@0.8.7"></script>
    <script src="https://wzrd.in/standalone/graphql-tag@1.2.4"></script>
  </head>
  <body>
    <div id="result"></div>
    <script src="index.js"></script>
  </body>
</html>
```

public/index.jsを次のように作成します。

```
const ApolloClient = apolloClient.default;
const gql = graphqlTag.default;
const client = new ApolloClient();

const query = gql`query {
  items {
    title
    description
  }
}`;

const showResult = ({ data: { items } }) => {
  const list = items.map(item => `<li>${item.title} - ${item.description}</li>`);
  document.getElementById('result').innerHTML = `<ul>${list}</ul>`;
};

client.query({ query }).then(showResult);
```

起動します。

```
$ node server
```

## 課題

1. 上記の例を動作させ、コードを理解する
2. GraphiQLでデータを入力して反映するか確認する
3. (挑戦) フォームを作成しaddItemを呼び出す
   - http://dev.apollodata.com/core/apollo-client-api.html#ApolloClient.mutate

## 参考情報

- http://dev.apollodata.com/core/apollo-client-api.html
