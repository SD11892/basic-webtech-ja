# アノテーション削除

型を定義するタイプアノテーションはJavaScriptでは文法エラーになります。

## コメントによる記法

コメントとしてタイプアノテーションを書く方法もあります。
この場合は文法エラーにはなりません。

```
// @flow

module.exports = (x /*: number*/) => x * 3;
```

## flow-remove-typesを使う

```
$ npm install flow-remove-types --save-dev
```

threetimes.js

```
// @flow

module.exports = (x: number) => x * 3;
```

```
$ $(npm bin)/flow-remove-types --out-dir out/ *.js
```

## babelを使う

```
$ npm install babel-cli babel-preset-flow --save-dev
```

package.jsonを編集する。

```
{
  ...
  "babel": {
    "presets": ["flow"]
  }
}
```

```
$ $(npm bin)/babel --out-dir out/ *.js
```

## 課題

1. 上記の動作を確認する
