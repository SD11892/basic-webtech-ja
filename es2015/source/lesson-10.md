# iterators

iteratorは内部的な機構です。arrayなどと連携します。またgeneratorとも関係します。

iteratorはループを回す時の統一的な仕組みです。

iterator objectは`next`メソッドを備え、それが呼び出されると
`value`と`done`というプロパティを持つオブジェクトを返します。

```
const array = [1, 2, 3, 4];
const iterator = array[Symbol.iterator]();
console.log(iterator.next());
console.log(iterator.next());
console.log(iterator.next());
console.log(iterator.next());
console.log(iterator.next());
console.log(iterator.next());
```

iteratorは配列とは異なります。例えば無限の長さのものも表現できます。

iteratorを提供するオブジェクトをiterableと言います。
iterableからiteratorを取り出すには上記のように `iterable[Symbol.iterator]()` としますが、この記述を直接書くことは稀かもしれません。

iterableはfor-ofでループを回せます。

```
for (const x of [1, 2, 3, 4]) {
  console.log(x);
}
```

ES5からあるfor-inはpropertiesを回すものなので混同しないようにしましょう。

## 課題

1. それぞれ動作を確認する

## 参考情報

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols
