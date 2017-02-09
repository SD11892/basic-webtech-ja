# array methods

## from

配列っぽいものから配列を作ります。

```
Array.from('javascript')
Array.from('javascript', x => `"${x}"`)
```

配列や文字列に加えてiterableも渡せます。

```
Array.from(Array(10).keys())
```

## of

配列を作ります。コンストラクタとほとんど同じですが、引数が一つの場合がより直感的になります。

```
Array(5, 4, 3)
Array(5, 4)
Array(5)
Array.of(5, 4, 3)
Array.of(5, 4)
Array.of(5)
```

## fill

配列の要素を全部同じもので埋めます。

```
[1, 2, 3, 4, 5, 6].fill(5)
[1, 2, 3, 4, 5, 6].fill(5, 2, 4)
```

## find,findIndex

配列から条件に合う要素を探します。

```
[0, 0, 3, 0, 2].find(x => x > 0);
[0, 0, 3, 0, 2].findIndex(x => x > 0);
```

## keys,entries,values

配列からiteratorを取得します。

```
Array.from(['a', 'b', 'c'].keys())
Array.from(['a', 'b', 'c'].entries())
```

`values`はNode v6では使えません。

## filter,map,reduce,every,some

ES5からありますが、これを機会に復習しましょう。

```
[1, 2, 3, 4, 5].filter(x => x > 3)
[1, 2, 3, 4, 5].map(x => x * 2)
[1, 2, 3, 4, 5].reduce((x, y) => x + y, 0)
[1, 2, 3, 4, 5].some(x => x > 3)
[1, 2, 3, 4, 5].every(x => x > 3)
```

## 課題

1. それぞれ動作を確認する

## 参考情報

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

## おまけ

- Array.prototypes.includesはES2016のものです
