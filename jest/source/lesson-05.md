# asyncテスト

非同期処理のテストも簡単に書けます。

## callback

```
const fs = require('fs');

test('async callback', (done) => {
  fs.readFile('package.json', 'utf8', (err, result) => {
    expect(err).toBeFalsy();
    expect(result).toContain('name');
    done();
  });
});
```

## promise

```
const asyncFunc = () => Promise.resolve('DUMMY TEXT');

test('async promise', () => {
  return asyncFunc().then((value) => {
    expect(value).toBe('DUMMY TEXT');
  });
});
```

promiseに慣れていない方はスキップしましょう。

## ドキュメント

詳しくは、下記のドキュメントを参照しましょう。

- https://facebook.github.io/jest/docs/asynchronous.html
- https://facebook.github.io/jest/docs/tutorial-async.html

## 課題

1. 上記の動作を確認する
