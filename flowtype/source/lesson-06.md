# 基本の型

- boolean
- string
- number
- null
- void

`string` はプリミティブタイプで `String` はオブジェクトタイプになります。

## 例

hello.js

```
// @flow

module.exports = (name: string) => `Hello ${name}`;
```

sayhello.js

```
// @flow

const hello = require('./hello');
console.log(hello('world'));
```

## チェックする

```
$ npm run flow
```

## 実行する

babel-nodeを使うのが簡単です。

```
$ $(npm bin)/babel-node sayhello.js
```

## 課題

1. 上記の動作を確認する
2. 他にも様々な例を書いてみる
