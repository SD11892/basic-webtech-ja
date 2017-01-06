# object shorthand

オブジェクトを作成するときに省略記法が導入されました。

```
const foo = 'abc';
const obj = { foo: foo };
```

を、

```
const foo = 'abc';
const obj = { foo };
```

と書くことができます。
大したことではありませんが、タイプ量が減るのと、ミスタイプのリスクが減ります。

また、

```
const obj = {
  f: function() {
    console.log('foo');
  },
  g: function(x) {
    console.log(x);
  },
};
```

を、

```
const obj = {
  f() {
    console.log('foo');
  },
  g(x) {
    console.log(x);
  },
};
```

と書くことができます。

ちなみに、アロー関数を使うと、次のように書くこともできます。

```
const obj = {
  f: () => {
    console.log('foo');
  },
  g: (x) => {
    console.log(x);
  },
};
```

ただし、アロー関数を使っていることから、同等ではありません。

## 課題

1. 省略記法で書いて動作を確認する

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Object_initializer
