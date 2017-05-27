# scriptsの書き方

package.jsonのscriptsエントリを使うと様々なタスクを簡単に実行できます。

## 簡単な例

例えば、eslintを実行するscriptは次のように書きます。

```
{
  "scripts": {
    "lint": "eslint"
  }
}
```

eslintのインストールや設定は完了しているものとします。この時、

```
$ npm run lint
```

とすることで、eslintを実行できます。 `./node_modules/.bin` がパスに入るため、プロジェクトレベルでインストールしたCLIツールを手軽に呼び出すことができます。

## scripts一覧

```
$ npm run
```

とすると、scriptsの一覧を見ることができます。node.jsのプロジェクトでは、scriptsがよく設定されているため、npm runで何が実行できるか分かることが多いです。

## あらかじめ用意されたscript名

`start`, `stop`, `test`などはrunを省略して、`npm start`などとして実行することができます。

また、`pre`, `post`などのprefixも定義されています。

`npm start`を実行すると、`prestart`, `start`, `poststart`の順に実行されます。





## 参考情報

- https://docs.npmjs.com/misc/scripts
