# 配列の型

## Array Type

```
const arr1: Array<number> = [1, 2, 3];
const arr2: number[] = [1, 2, 3];
const arr3: Array<string> = ['a', 'b', 'c'];
const arr4: string[] = ['a', 'b', 'c'];
```

## Tupple Type

タプルはJavaScriptでは固定長の配列で実現されます。
flowでは可変長の配列とは区別されます。

```
const tuple1: [string, string] = ['first', 'last'];
const tuple2: [string, number] = ['apple', 3];
```

タプルは可変長の配列ではないので、破壊的なArrayのメソッドは使えません。

```
tuple1.push('oops');
```

## 課題

1. 上記の動作を確認する
2. 他にも色々動作を確認する

# その他の型

これまで見てきた型はごく一部であり、他にも様々なものが用意されています。
詳細はドキュメントを参照しましょう。
https://flow.org/en/docs/types/

- maybe types
- mixedとany
