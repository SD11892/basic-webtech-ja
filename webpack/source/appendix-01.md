# webpack-dev-middleware

webpack-dev-serverの内部ではexpress middlewareであるwebpack-dev-middlewareが使われています。
Expressサーバをすでに導入している場合はこのmiddlewareを使うことで統合できます。

開発向けとプロダクション向けの切り分けがポイントになります。
一例として、express-react-reduxの仕組みが参考になるかもしれません。

https://www.npmjs.com/package/express-react-redux

## 参考情報

- https://github.com/webpack/webpack-dev-middleware
