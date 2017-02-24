# サーバのコード例

Apolloを使うと簡単にGraphQLのサーバーを構築できます。

## 構築方法

はじめにパッケージをインストールします。

```
$ npm init -y
$ npm install express body-parser graphql graphql-tools graphql-server-express --save
```

server.jsを次のようにします。

```
const express = require('express');
const bodyParser = require('body-parser');
const { graphqlExpress, graphiqlExpress } = require('graphql-server-express');
const { makeExecutableSchema } = require('graphql-tools');

const typeDefs = [`
  type Item {
    title: String
    description: String
  }
  type Query {
    items: [Item]
  }
  type Mutation {
    addItem(title: String, description: String): Boolean
  }
`];

const items = [{
  title: 'apple',
  description: 'pie',
}, {
  title: 'orange',
  description: 'pie',
}];

const resolvers = {
  Query: {
    items: () => items,
  },
  Mutation: {
    addItem: (obj, { title, description }) => !!items.push({ title, description })
  },
};

const app = express();
app.use(bodyParser.json());
app.use('/graphql', graphqlExpress({
  schema: makeExecutableSchema({ typeDefs, resolvers }),
}));
app.use('/graphiql', graphiqlExpress({ endpointURL: '/graphql' }));
app.listen(process.env.PORT || 3000);
```

起動は次のようにします。

```
$ node server
```

http://localhost:3000/graphiql でアクセスできます。

## 課題

1. GrahiQLで動作を確認する
2. スキーマにコメントを追加する
3. スキーマを修正してみる
4. (挑戦) resolversを修正してみる

## 参考情報

- http://dev.apollodata.com/tools/
