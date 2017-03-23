# mockテスト

単体テストにおいてテスト対象ではないコードの動きをダミーにするのにmockを使います。

## mock関数

mock関数を使うとその関数の呼び出しの履歴を記録することができます。
また、その関数の実装も指定することができます。

array.test.jsというファイルを作成します。

```
test('array filter', () => {
  const func = jest.fn();
  [1, 2, 3, 4].filter(func);
  expect(func).toHaveBeenCalled();
});

test('array some with returning true', () => {
  const func = jest.fn(() => true);
  [1, 2, 3, 4].some(func);
  expect(func).toHaveBeenCalledTimes(1);
});

test('array some with returning false', () => {
  const func = jest.fn(() => false);
  [1, 2, 3, 4].some(func);
  expect(func).toHaveBeenCalledTimes(4);
});
```

### テスト実行

```
$ npm test array.test.js
```

### ドキュメント

詳しくは、下記のドキュメントを参照しましょう。

- https://facebook.github.io/jest/docs/mock-function-api.html
- https://facebook.github.io/jest/docs/expect.html#tohavebeencalled
- https://facebook.github.io/jest/docs/expect.html#tohavebeencalledtimesnumber
- https://facebook.github.io/jest/docs/expect.html#tohavebeencalledwitharg1-arg2- https://facebook.github.io/jest/docs/expect.html#tohavebeenlastcalledwitharg1-arg2-

## jest.mock

`jest.mock`を使うと、requireするライブラリをmock関数化できます。
また、factoryを指定して実装を変更することもできます。

fs.test.jsというファイルを作成します。

```
test('fs readFileSync', () => {
  jest.resetModules();
  jest.mock('fs');
  const fs = require('fs');
  fs.readFileSync('package.json', 'utf8');
  expect(fs.readFileSync).toHaveBeenCalledTimes(1);
});

test('fs readFileSync with factory', () => {
  jest.resetModules();
  jest.mock('fs', () => ({
    readFileSync: jest.fn(() => 'DUMMY TEXT'),
  }));
  const fs = require('fs');
  const text = fs.readFileSync('package.json', 'utf8');
  expect(fs.readFileSync).toHaveBeenCalledTimes(1);
  expect(text).toBe('DUMMY TEXT');
});
```

### テスト実行

```
$ npm test fs.test.js
```

### ドキュメント

詳しくは、下記のドキュメントを参照しましょう。

- http://facebook.github.io/jest/docs/jest-object.html#jestmockmodulename-factory-options
- https://facebook.github.io/jest/docs/jest-object.html#jestresetmodules

## 課題

1. 上記の動作を確認する
2. mock関数を使ったテストコードを書く
3. jest.mockを使ったテストコードを書く
