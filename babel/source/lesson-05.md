# babel-node

サーバサイドでbabelを使う場合はbabel-nodeが使えます。

```
$ $(npm bin)/babel-node --presets es2015
> const x = () => 1
```

ところで、Node v6を使っている場合はes2015は
[99%サポート](http://node.green)されているため、
es2015プリセットはほとんど意味がありません。
仮に、Node v4を使う必要がある場合には意味があります。

無理矢理試すとすると、Nodeでは`Array.prototype.values`が
(わざと)サポートされていないので、それで比較できます。

```
$ $(npm bin)/babel-node --presets es2015
> [1, 2, 3].values()
{}
```

```
$ node                  
> [1, 2, 3].values()
TypeError: [1,2,3].values is not a function
```

babelはes2015以外にも使うシーンがあり、その場合は、
Node.jsの開発環境において使う場合にはbabel-nodeは便利です。
ただし、プロダクション環境では使わないようにする方がよいでしょう。

## 課題

1. 上記を動作させる
2. NodeではサポートされていないES modulesをbabel-nodeで動かしてみる

## 参考情報

- https://babeljs.io/docs/usage/cli/#babel-node
