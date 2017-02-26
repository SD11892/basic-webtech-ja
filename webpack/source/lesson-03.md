# 基本的な使い方

CLIで基本的な使い方を学びましょう。

## サンプルファイル作成

下記のようにファイルを作成を作ります。

public/index.html

```
<html>
  <body>
    <div id="app"></div>
    <script src="bundle.js"></script>
  </body>
</html>
```

src/index.js

```
import moment from 'moment';

document.getElementById('app').innerHTML = 'The time now is ' + moment().toString();
```

webpack v2ではES modulesのimportがサポートされています。

## 依存パッケージのインストール

上記のjsファイルではmomentというパッケージを使っていますのでそれをインストールします。

```
$ npm install moment --save-dev
```

## ビルド実行

webpackでビルドします。

```
$ $(npm bin)/webpack src/index.js public/bundle.js
```

今後のためにpackage.jsonにscriptを書いておきましょう。

```
{
  "scripts": {
    "build-bundle-js": "webpack src/index.js public/bundle.js"
  }
}
```

上記scriptは置き換えずにマージしてください。

このようにすると、次のように実行できます。

```
$ npm run build-bundle-js
```

## 結果確認

public/index.htmlをブラウザで開きましょう。

bundle.jsの中身を眺めてみましょう。自分が書いたコード以外にもmoment.jsのコードが含まれています。

## 課題

1. 上記の動作を確認する
2. (挑戦) moment以外のパッケージを使って見る

## 参考情報

- https://webpack.js.org/guides/get-started/
