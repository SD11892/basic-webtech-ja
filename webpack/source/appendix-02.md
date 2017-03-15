# server-side webpack

webpackは主にブラウザ向けのビルドツールですが、Node.jsにおいて使うことも可能です。
サーバサイドで使う場合にメリットがあるシーンとしては、

- server-side rendering (SSR)
- hot module replacement (HMR)

があります。
Reactアプリの例はいくつか知られているので調べてみましょう。

一方、Expressなどの完全なバックエンドでHMRを実現するためにwebpackを使うことは、それほど情報がないですが、可能だと思われます。

## 参考情報

- https://github.com/webpack/react-webpack-server-side-example
