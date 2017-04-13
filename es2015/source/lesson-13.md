# promises

Promiseは以前からライブラリとして提供されていました。
機能としてはライブラリで実現できるものですが、
標準として共通化されることには意味があるでしょう。

## 基本の形

```
const fs = require('fs');

const promise = new Promise((resolve, reject) => {
  fs.readFile('package.json', 'utf8', (err, result) => {})
    if (err) {
      reject(err);
    } else {
      resolve(result);
    }
  });
});

promise.then((result) => { console.log(result); });
```

## 例外

```
promise.then(
  (result) => { console.log(result); },
  (reason) => { console.error(reason); }
);

promise
  .then((result) => { console.log(result); })
  .catch((reason) => { console.error(reason); });

```

## チェイン

```
const delay = value => new Promise((resolve) => {
  setTimeout(() => resolve(value), 1000);
});

promise
  .then((result) => delay(result))
  .then((result) => { console.log(result); })
  .catch((reason) => { console.error(reason); });
```

## 並列処理

```
Promise.all([promise1, promise2, promise3])
  .then(([result1, result2, result3]) => {
    console.log(result1);
    console.log(result2);
    console.log(result3);
  });
```

1つだけ完了するのを待つにはPromise.raseを使います。

## その他

Promise.resolve, Promise.reject

## 課題

1. 基本的な動作を確認する
2. MongoDB node.js driverを使って動作を確認する

## 参考情報

- https://ja.wikipedia.org/wiki/Future
- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise
- https://promisesaplus.com
