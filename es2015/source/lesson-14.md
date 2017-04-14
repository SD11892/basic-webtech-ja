# proxies

ライブラリ開発では使うかもしれませんが、アプリ開発で直接使うことはあまりないかと思います。参考程度に。

これまでもgetter/setterは使えましたが、proxyはさらに強力です。
動的にgetter/setterがtrapできたり、それ以外のメソッドもtrapできます。

## 例

```
const foo = new Proxy({}, {
  get: (obj, prop) => { console.log('getting', prop); return obj[prop]; },
  set: (obj, prop, val) => { console.log('setting', prop); obj[prop] = val; },
});

foo.a = 1;
foo.b = foo.a + 2;
```

## 課題

1. 上記の動作を確認する

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy 
