# ブラウザテスト

jestはもともとはクライアントコードをテストするライブラリで、
デフォルトの環境もjsdomになっています。

## jsdom環境

package.jsonの `testEnvironment: "node"` を指定しないか、
テスト実行時に下記のようにenvを指定すると、jsdom環境でテストが動きます。

```
$ npm test -- --env=jsdom
```

## jqueryを使ったテスト

jqueryをインストールします。

```
$ npm install jquery --save
```

jquery.test.jsを作成します。

```
const $ = require('jquery');

test('jquery test', () => {
  $('<h1>').text('Hello').appendTo('body');
  expect(document.body.innerHTML).toBe('<h1>Hello</h1>');
});
```

テストを実行します。

```
$ npm test -- --env=jsdom jquery.test.js
```

今回は簡単のためテストコードでの動作確認ですが、
テスト対象のコードとテストコードが分離していても同じようにできます。

## ドキュメント

詳しくは、下記のドキュメントを参照しましょう。

- https://facebook.github.io/jest/docs/tutorial-jquery.html

## 課題

1. 上記の動作を確認する
2. テスト対象のコードを用意して、それについてテストコードを書く
