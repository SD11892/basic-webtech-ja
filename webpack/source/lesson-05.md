# プロダクションビルド

webpackでは開発向けのビルドとプロダクション向けのビルドを切り替えることができます。
自分でカスタマイズすることもできますが、まずはwebpackが用意している`-p`オプションの動きを見てみましょう。

## package.jsonの修正

下記を追加します。

```
{
  "scripts": {
    "build-bundle-js-for-prod": "webpack -p --module-bind js=babel-loader src/index.js public/bundle.js"
  }
}
```

## 結果確認

```
$ npm run build-bundle-js-for-prod
```

でビルドしてから、bundle.jsの中身を眺めてみましょう。
minificationが効いているはずです。

## 様々な設定方法

`-p`オプション以外にもカスタマイズ可能な様々な方法があります。

- configファイルを完全に分ける
- envオプションを指定して分ける
- process.env.NODE_ENVを指定して分ける　

## 課題

1. 上記の動作を確認する

## 参考情報

- https://webpack.js.org/guides/production-build/
- https://webpack.js.org/guides/environment-variables/
