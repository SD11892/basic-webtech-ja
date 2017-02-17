# REPL

まずは、Babelがどういうことをしてくれるのか試してみましょう。

BabelのサイトにあるTry it outを開きます。

http://babeljs.io/repl/

左にコードを入力すると、右に変換されたコードが表示されます。

例えば、次のように入力してみましょう。

```
const x = 1;
let y = 1;
```

では、その次に `x = 2;` を追記したらどうなるでしょう？

### アロー関数

```
const f = () => 1;
```

もう少し複雑な例を試しましょう。

```
const f2 = function() {
  const x = () => { this.y = 1; };
};
```

### 分割代入

```
const arr = [1, 2, 3];
const [a, b] = arr;
const [c, ...rest] = arr;
```

オブジェクトも試しましょう。

```
const obj = { a: 1, b: 2, c: 3 };
const { a, b } = obj;
```

変数名が重複しているので、以前のコードは消すか、変数名を変えてください。

## 課題

1. 上記を動作させる
2. 他にも色々試してみる

## 参考情報

- http://babeljs.io/learn-es2015/
