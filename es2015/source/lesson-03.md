# constとlet

`const`および`let`はES5の`var`を置き換えるものです。
`const`は定数を宣言するもので、`let`が変数を宣言するものです。
役割としては`let`が`var`と同様のものですが、同一ではないため別の名前になっています。

## 再代入の可否

`const`と`let`の差異は再代入の可否です。`const`は再代入が禁止されます。

```
const x = 1;
x = 2; // error
let y = 3;
y = 4; // ok
```

constでオブジェクトや配列を定義した場合にその要素を書き換えることは再代入にはなりません。

```
const o = {};
o.a = 1; // ok
const a = [];
a[0] = 2; // ok
```

## ブロックスコープ

`var`は関数スコープという多少分かりにくいスコープの概念でしたが、
`const`と`let`はブロックスコープになりより直感的に使えます。

```
function f() {
  var x = 1;
  if (true) {
    var x = 2; // same as x = 2;
  }
  console.log(x); // display "2"
}

function g() {
  let x = 1;
  if (true) {
    let x = 2; // different from outer x
  }
  console.log(x); // display "1"
}
```

一方で、同一変数名をネスとしたブロックスコープで使って変数を隠してしまうことは、
バグの元にもなるので一般的には勧められるものではありません。

参照: http://eslint.org/docs/rules/no-shadow

## varにしかできないこと

- 関数スコープの変数の宣言
- (ファイルを横断する)グローバル変数の宣言

## おすすめ

- `var`は一切使わない
- 再代入を行わないケースでは必ず`const`を使う

## 課題

1. 再代入の可否について試す

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/const
- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/let
