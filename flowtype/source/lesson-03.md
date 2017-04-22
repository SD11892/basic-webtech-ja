# 最初の例

## ファイル作成

main.jsを作ります。

```
// @flow

const threetimes = x => x * 3;

console.log(threetimes(2));
```

## flowの実行

```
$ npm run flow
```

## ファイルの修正

main.jsのを下記のように書き換えます。

```
// @flow

const threetimes = x => x * 3;

console.log(threetimes('a'));
```

### flowの再実行

```
$ npm run flow
```

## 課題

1. 上記の動作を確認する
2. 他にも例を試してみる
