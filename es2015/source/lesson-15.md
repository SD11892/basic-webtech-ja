# tail calls

ES2015で規定された少し珍しい機能としてproper tail callsがあります。
これを規定・実装しているプログラミング言語はそれほど多くありません。

https://en.wikipedia.org/wiki/Tail_call#By_language

proper tail callsが実装された環境では、末尾再帰関数がループの代わりに使えます。

## Node v6での利用法

http://node.green
を参照するとわかるようにFlagが必要です。
具体的には次のように起動します。

```
$ node --harmony --use_strict
```

## 簡単な例

階乗の計算をしてみましょう。

x! = x * (x - 1) * (x - 2) * ... * 1

つまり、

1! = 1
x! = x * (x - 1)!

です。これをそのままJSコードに変換すると、

```
const f = x => x === 1 ? 1 : x * f(x - 1);
```

になります。これは再帰関数ですが、残念ながら末尾再帰ではありません。

末尾再帰に変換すると、

```
const f = (x, a=1) => x === 1 ? a : f(x - 1, a * x)
```

になります。

参考までにループで書くと、

```
const f = (x) => {
  let a = 1;
  for (let i = 1; i <=x; i += 1) {
     a *= i;
  }
  return a;
};
```

となります。
こちらの方が良いと感じる場合はあまり末尾再帰に魅力はないかもしれません。

## 少し実用的な例

数値の配列の加算をする関数を考えましょう。

Array.reduceを使うと次のようになります。

```
const sum = arr => arr.reduce((x, p) => p + x, 0);
```

末尾再帰で書くと、例えば、次のようになります。

```
const sum = ([num=0, ...rest], result=0) =>
  rest.length === 0 ? result + num : sum(rest, result + num);
```

他にも様々な例がありえます。
再帰関数のうちループでかけるものは必ず末尾再帰に変換できます。

## お遊びの例

```
const mugen = () => { console.log('mugen'); return mugen(); };
```

```
const count = (c=1) => { console.log(c); return count(c + 1); };
```

proper tail callはスタックを消費しないので、関数が一生戻らなくても問題ありません。

```
const apple = () => { console.log('apple'); return pen(); };
const pen = () => { console.log('pen'); return apple(); };
```

## 課題

1. 階乗のコードをharmonyフラグなしで実行する
2. 階乗のコードをharmonyフラグ付きで実行する
3. 他の例も試す
4. 自分で末尾再帰関数を書いてみる

## 参考情報

- https://babeljs.io/learn-es2015/#ecmascript-2015-features-tail-calls
- https://medium.com/@dai_shi/tail-call-optimization-tco-in-node-v6-e2492c9d5b7c
