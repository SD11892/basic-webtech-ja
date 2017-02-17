# plugins

これまで、es2015というプリセットを使いましたが、これはプラグインの組み合わせです。

https://babeljs.io/docs/plugins/preset-es2015/

それぞれのプラグインが変換の機能を備え、それを有効にすることで動作します。
つまり、プラグイン（やプリセット）を指定しないでbabelを実行すると何も変換が起こりません。

プラグインを有効にするには、--pluginsや設定ファイル(package.jsonや.babelrc)で指定する必要があります。

試しに、es2015のプリセットを使わずにpluginだけを使ってみましょう。

```
$ $(npm bin)/babel-node --plugins transform-es2015-destructuring
> var [x, y] = [1, 2]
```

利用するプラグインの数を絞るとコンパイルにかかる時間を減らすことができます。

他にも、es2015プリセットに含まれていないプラグインがあります。
Redux等でオススメなのはobject-rest-spreadです。標準化されるかは分かりません。

https://babeljs.io/docs/plugins/transform-object-rest-spread/

### 非公式プラグイン

Babelのプラグインは誰でもつくることができnpm等で公開されています。

https://www.npmjs.com/search?q=babel-plugin

これらも公式プラグインと同様にインストールして設定すれば使うことができます。

## 課題

1. 上記の動作を確認する
2. 他にどんなプラグインがあるか見る

## 参考情報

- https://babeljs.io/docs/plugins/
