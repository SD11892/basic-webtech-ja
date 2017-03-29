# nodeテスト

最初にnodeでの単体テストを書いてみましょう。

## 対象コード

src/sum.jsというファイルを作成します。

```
exports.sum = (a, b) => a + b;
exports.sum3 = (a, b, c) => a + b + c;
exports.sumList = (...list) => list.reduce(sum, 0);
```

## テストコード

src/sum.test.jsというファイルを作成します。

```
const { sum, sum3, sumList } = require('./sum');

describe('sum test', () => {
  it('adds 1 + 2', () => {
    expect(sum(1, 2)).toBe(3);
  });
  it('adds 2 + 5', () => {
    expect(sum(2, 5)).toBe(7);
  });
  it('adds -3 + 5', () => {
    expect(sum(-3, 5)).toBe(2);
  });
});
```

このファイルは`__tests__/sum.js`や`src/__tests__/sum.js`などとすることもできます。

## ドキュメント

テストで使われている関数等の詳細については、下記のドキュメントを参照しましょう。

- http://facebook.github.io/jest/docs/api.html#describename-fn
- http://facebook.github.io/jest/docs/api.html#testname-fn
- http://facebook.github.io/jest/docs/expect.html#expectvalue
- http://facebook.github.io/jest/docs/expect.html#tobevalue

## テスト実行

```
$ npm test
```

## 課題

1. 上記の動作を確認する
2. `sum3` のテストコードを書く
3. `sumList` のテストコードを書く
