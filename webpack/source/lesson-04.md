# ES2015対応

ES2015はまだすべてのブラウザでサポートされていないので、
Babelでトランスパイルする必要があります。

Webpack v2ではES modulesだけサポートされているので注意が必要です。

## サンプルファイルの更新　

src/index.jsを次のようにしてみましょう。

```
import moment from 'moment';

const render = () => {
  document.getElementById('app').innerHTML = `The time now is ${moment().toString()}`;
};

render();
```

## Babelのインストール

```
$ npm install babel-core babel-loader babel-preset-es2015 --save-dev
```

## package.jsonの修正

ビルドスクリプトを書き換え、さらにBabelの設定を追加します。

```
{
  "scripts": {
    "build-bundle-js": "webpack --module-bind js=babel-loader src/index.js public/bundle.js"
  },
  "babel": {
    "presets": [
      ["es2015", { "modules": false }]
    ]
  }
}
```

## 結果確認

ビルドしてから、public/index.htmlをブラウザで開きましょう。

bundle.jsの中身を眺めてみましょう。ES2015のコードがES5に変換されています。

## 課題

1. 上記の動作を確認する
2. (挑戦) Reactを使えるように設定する

## 参考情報

- https://webpack.js.org/api/cli/
