# callback/promise復習

## callback

```
const hello = (name, callback) => {
  const message = `Hello ${name}!`;
  setTimeout(() => {
    callback(null, message); // the first argument is for error
  }, 3000);
};
```

```
const main = () => {
  hello('world', (err, str) => {
    if (err) {
      console.error(err);
    } else {
      console.log(str);
    }
  });
};

console.log('START');
main();
```

## promise

```
const hello = (name) => {
  const message = `Hello ${name}!`;
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(message);
    }, 3000);
  });
};
```

```
const main = () => {
  hello('world').then((str) => {
    console.log(str);
  }).catch((err) => {
    console.error(err);
  });
};

console.log('START');
main();
```

## 課題

1. 上記を動作させる
2. (挑戦) Promise.resolveを使ってみる
