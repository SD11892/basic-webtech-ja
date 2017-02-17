# CLI

ツールをインストールします。

```
$ npm install babel-cli babel-preset-es2015
```

## ファイルの作成

file-es2015.js

```
const x = 1;
let y = 2;
```

## コマンド実行

```
$ $(npm bin)/babel --presets es2015 file-es2015.js -o file-es5.js
```

file-es5.jsの中身を確認しましょう。

## ディレクトリ単位で実行

その場合は次のようにします。

```
$ $(npm bin)/babel --presets es2015 src --out-dir dest
```

## package.jsonに書く

package.jsonに書く場合は次のようにします。

```
{
  "scripts": {
    "compile": "babel src --out-dir dest"
  },
  "babel": {
    "presets": ["es2015"]
  }
}
```

実行は、次のようになります。

```
$ npm run compile
```

babelセクションは.babelrcに書くこともできます。

## 課題

1. 上記を動作させる
2. 他にもファイルを作成してコマンドを実行してみる

## 参考情報

- https://babeljs.io/docs/usage/cli/
