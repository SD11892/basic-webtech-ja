# webpack-dev-server

これまでの方法だと、ファイルを保存した後にブラウザのリロードボタンを押す必要がありました。
webpac-dev-serverを使うと、開発時にリロードの手間を省くことができます。

## インストール

```
$ npm install webpack-dev-server --save-dev
```

> Note: There are known issues with Node.js v7 and webpack / webpack-dev-server. Please use Node.js v6 for the moment.

## package.jsonの更新

package.jsonに例えば次のように書きます。

```
{
  "scripts": {
    "webpack-dev-server": "webpack-dev-server"
  }
}
```

タイピングを楽にするためには、左を"dev-server"などにするとよいかもしれません。
(npm runは補完も効きますが)

## publicPathの設定

webpack.config.jsにpublicPathの設定を追加します。

```
module.exports = {
  entry: './src/index.js',
  output: {
    path: __dirname + '/public',
    publicPath: '/public',
    filename: 'bundle.js'
  },
  module: {
    rules: [{ test: /\.js$/, use: 'babel-loader' }]
  },
  plugins: []
};
```

## 起動

下記を実行します。

```
$ npm run webpack-dev-server
```

その後、 http://localhost:8080/webpack-dev-server/public/ を開きます。

## カスタマイズ

CLIのオプションは下記で確認できます。

```
$ $(npm run)/webpack-dev-server --help
```

また、webpack.config.jsでもカスタマイズが可能です。

https://webpack.js.org/configuration/dev-server/ 

## 課題

1. dev-serverの動作を確認する(ファイルを変更してブラウザに反映されるか)
2. (挑戦) URLからpublicをなくすように設定する
3. (挑戦) inline modeを試してみる

## 参考情報

- https://github.com/webpack/webpack-dev-server
- https://webpack.js.org/guides/public-path/
