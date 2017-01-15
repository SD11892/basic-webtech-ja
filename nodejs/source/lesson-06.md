# CLIスクリプトを作る

CLIツールを作ることは比較的簡単です。

CLIで動くスクリプトにするには、shebangをつけます。一般的には次のようなものが多いです。

```
#!/usr/bin/env node
```

ただし、UNIX系でしか使えません。
また、`chmod +x`で実行フラグを立てます。

コマンドライン引数を受け取るには`process.argv`を使います。

```
#!/usr/bin/env node

const name = process.argv[2] || 'unknown';
console.log(`Hello ${name}!`);
```

## 便利パッケージ

- https://www.npmjs.com/package/commander
  - 高機能なコマンドを作る時に便利です
- https://www.npmjs.com/package/fs-extra
  - `fs`を拡張するパッケージ

## パッケージ化

package.jsonを作ると、依存パッケージを定義したり、npm scriptsを定義したりできます。
また、npmで公開することもできます。

## 課題

- 試しに何か作ってみる

## 参考情報

- https://developer.atlassian.com/blog/2015/11/scripting-with-node/
- http://sitest.jp/blog/?p=3712
- https://nodejs.org/dist/latest-v6.x/docs/api/process.html
