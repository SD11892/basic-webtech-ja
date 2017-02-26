# webpack config

webpackを使いこなすにはカスタマイズが必要になります。
実際にはCLIのオプションだけでは書ききれずに、configファイルを記述することになります。

## configファイルの名前

CLIのオプションで指定できますが、デフォルトでは、 webpack.config.js もしくは webpackfile.js が読み込まれます。

ここではよく使われる webpack.config.js を使います。

## webpack.config.jsの中身

通常のJavaScriptのファイルです。
configオブジェクトかそれを返す関数をexportします。
いろいろな書き方が可能ですが、基本はstatic objectを返します。

```
module.exports = {
  entry: './src/index.js',
  output: {
    path: __dirname + '/public',
    filename: 'bundle.js'
  },
  module: {
    rules: [{ test: /\.js$/, use: 'babel-loader' }]
  },
  plugins: []
};
```

これができれば、CLIのオプションは不要になります。

```
{
  "scripts": {
    "webpack": "webpack"
  }
}
```

のようにして `npm run webpack` で実行するか `$(npm bin)/webpack` でも実行できます。

### modules

サポートするモジュールを列挙します。
ルールを指定してファイルごとにloaderを指定します。

今回はbabel-loaderを使いましたが、他にもfile-loaderやcss-loaderなどあります。

公式loaderのリストはこちらです: https://webpack.js.org/loaders/

コミュニティによるloaderの実装も数多くあります。

### plugins

さらに機能を拡張するためのプラグインを指定できます。

例えば、HtmlWebpackPluinを使うと、bundle.jsを組み込んだHTMLファイルを生成できます。

また、プロダクションビルドでは`webpack.optimize.UglifyJsPlugin`が使われていました。

公式pluginのリストはこちらです: https://webpack.js.org/plugins/

コミュニティによるpluginの実装も数多くあります。

## 課題

1. 上記の動作を確認する
2. (挑戦) 他のloaderも使ってみる
3. (挑戦) 他のpluginも使ってみる

## 参考情報

- https://webpack.js.org/guides/get-started/#using-webpack-with-a-config
- https://webpack.js.org/concepts/
- https://webpack.js.org/concepts/modules/
- https://webpack.js.org/concepts/plugins/
- https://webpack.js.org/configuration/
