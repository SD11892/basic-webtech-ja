# Promise.race

Promise.allは全部の終了を待つものですが、一つだけを待つ場合はPromise.raceを使います。

## 例

```
const timer = async (timeout, result) => 
  new Promise(resolve => setTimeout(() => resolve(result), timeout));

const main = async () => {
  const result = await Promise.race([
    timer(3000, 'slowest'),
    timer(2000, 'slower'),
    timer(1000, 'slow'),
  ]);
  console.log(result);
};
```

## 課題

1. 上記を動作させる
2. Promise.raceをPromise.allに置き換えて動作をみる
