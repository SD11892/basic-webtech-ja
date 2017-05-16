# sequence

Promise.allは並列処理でしたが、逐次処理をしたい場合はどうすればよいでしょう。
個数が決まっている場合はすべて書く方法もありますが、可変の場合はうまくループさせる必要があります。

参考リンク：
http://stackoverflow.com/questions/24586110/resolve-promises-one-after-another-i-e-in-sequence

## Promise.sequence

```
Promise.sequence = tasks => tasks.reduce(async (promise, task) => {
  await promise;
  return task();
}, Promise.resolve());
```

のように定義しておくと簡単に使えるかもしれません。
気をつけるべきは、taskはpromiseを返す関数でなければいけないことです。

## 使用例

```
const timer = async (timeout, result) => 
  new Promise(resolve => setTimeout(() => {
    console.log('done', { timeout, result });
    resolve(result);
  }, timeout));

const main = async () => {
  const arr = ['mesg1', 'mesg2', 'mesg3'];
  const result = await Promise.sequence(arr.map(mesg => () => timer(1000, mesg)));
  console.log(result);
};
```

## 課題

1. 上記を動作させる
2. (挑戦) 逐次処理をするけれど結果を配列で返すにはどうするか
