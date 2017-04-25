# オブジェクトの型

## オブジェクトの作成

objtest.js

```
// @flow

const obj = { num: 3, str: 'a' };
const len1 = obj.num.length; // error
const len2 = obj.str.length;
const num1 = obj.num * 2;
const num2 = obj.str * 2; // error
const nonexistence = obj.foo; // error
```

より明示的に型を指定する。

```
// @flow

const obj: { num: number, str: string, foo?: string } = { num: 3, str: 'a' };
const len1 = obj.num.length; // error
const len2 = obj.str.length;
const num1 = obj.num * 2;
const num2 = obj.str * 2; // error
const nonexistence = obj.foo; // ok now
```

## オブジェクトの作成その2

```
// @flow

const obj = {};
obj.num = 3;
obj.str = 'a';
const len1 = obj.num.length; // error
const len2 = obj.str.length;
const num1 = obj.num * 2;
const num2 = obj.str * 2; // error
const nonexistence = obj.foo; // ok
```

## オブジェクトの作成その3

```
// @flow

const obj = {};
if (Math.random() > 0.5) {
  obj.foo = 'str';
} else {
  obj.foo = 9;
}

const num: number = obj.foo; // error

obj.foo = 3;

const num2: number = obj.foo; // ok
```

## 課題

1. 上記の動作を確認する
2. 他にも色々動作を確認する
