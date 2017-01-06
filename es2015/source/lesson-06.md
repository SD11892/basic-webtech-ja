# destructuring object/array

オブジェクトや配列の構造を分解して変数に代入することができます。

```
const obj = { a: 1, b: 2};
const { a, b } = obj;
const arr = [1, 2];
const [x, y] = arr;
```

余分な要素があっても大丈夫です。

```
const obj = { a: 1, b: 2, c: 3 };
const { a, b } = obj;
const arr = [1, 2, 3];
const [x, y] = arr;
```

## 課題

1. 様々な例を作って動作を確認する

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
