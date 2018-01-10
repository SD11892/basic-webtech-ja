# arguments default/rest/spread

関数の引数において、新しい記法が導入されました。

```
const f = (x = -1) => { console.log(x); };
f(1);
f(2);
f();
const g = (a, b, c = {}) => { console.log(a, b, c); };
```

引数を省略できます。

```
const func = (a, b, ...c) => { console.log(a, b, c); };
func(1, 2, 3, 4, 5);
```

残りを配列で受け取れます。

```
const a = [4, 5, 6];
func(1, 2, 3, ...a);
func(...a);
```

配列を展開して引数に渡せます。

## 課題

1. 新しい記法で書いて動作を確認する

## 参考情報

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator
