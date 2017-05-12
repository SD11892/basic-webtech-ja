# async導入

先ほどのpromiseの例をasync/awaitを使って書くと次のようになります。

```
const main = async () => {
  try {
    const str = await hello('world');
    console.log(str);
  } catch(err) {
    console.error('ERROR', err);
  }
};
```

## 例外

エラーをテストするにはhelloを次のように書き換えます。

```
const hello = (name) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      reject('oops')
    }, 3000);
  });
};
```

## 課題

1. 上記を動作させる
2. (挑戦) asyncを使ってpromiseを返す関数を作る(main -> helloworld -> hello)
