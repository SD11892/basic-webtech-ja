# array rest/spread

配列において、新しい記法が導入されました。

```
const [x, y, ...z] = [1, 2, 3, 4, 5];
```

残りの要素を全て配列として取れます。

```
const a = [2, 3, 4];
const b = [...a, 5, 6];
const c = [0, 1, ...a, 5, 6];
const d = [0, 1, ...a];
```

配列を配列中で展開できます。

## 課題

1. 新しい記法で書いて動作を確認する

## 参考情報

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator
