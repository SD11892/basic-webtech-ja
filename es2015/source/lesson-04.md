# arrow function

アロー関数は、関数の新しい構文です。無名関数を作成するのに使います。
構文が簡素になっただけでなく、`this`の扱いにも変化があります。

```
const f = function() {
  console.log('hello');
};
```

が、

```
const f = () => {
  console.log('hello');
};
```

と書けます。`function`の代わりに`=>`という矢印（アロー）になりました。

## thisの扱い

通常の`function`では`this`は関数の呼び出しコンテキストになりますが、
アロー関数の場合は、`this`はアロー関数の外側の`this`と同じになります。

```
const f1 = function() {
  this.counter = 0;
  const g = function() { this.counter = 1; };
  const obj = { func: g, counter: 100 };
  obj.func(); // g.call(obj);
  console.log(this.counter, obj.counter);
};

const f2 = function() {
  this.counter = 0;
  const g = () => { this.counter = 1; };
  const obj = { func: g, counter: 100 };
  obj.func(); // g.call(obj);
  console.log(this.counter, obj.counter);
};
```

## 省略記法

アロー関数の中身が`return`文だけの場合は文を省略して値を返すことができます。

```
const f = () => { return "foo"; };
```

は、

```
const f = () => "foo";
```

と書けます。オブジェクトを返す場合は`()`で囲う必要があります。

```
const f1 = () => { return { foo: 'bar' }; };
const f2 = () => ({ foo: 'bar' });
```

アロー関数の引数のカッコは、引数が1つだけの場合(0でも2以上でもない場合)に省略することができます。

```
const f1 = (x) => { console.log(x); };
const f2 = x => { console.log(x); };
```

ただし、これは自由度が高いため、統一した記法に揃えることがお勧めです。
一つの方針は、アロー関数の本体が`{}`のブロックではなく値を直接返す場合のみ引数のカッコを省略するというものです。これは、eslint-config-airbnbで規定されています。

## 課題

1. 省略記法と省略しない記法で同じ関数を書いて動作を確認する
2. (挑戦)thisの扱いの動作を確認する

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/arrow_functions
