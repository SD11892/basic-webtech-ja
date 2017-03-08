# ページ作成

next.jsではフォルダ構造を使ってページを作ります。

## フォルダ構造

```
./pages
./pages/index.js
./pages/foo.js
./pages/bar.js
./pages/hoge/index.js
./pages/hoge/fuga.js
```

この構造がそのままURLに反映されます。

## ファイルの中身

Reactコンポーネントで書きます。

./pages/index.jsを作ります。

```
import React from 'react';

export default () => (
  <div>
    <h1>Hello Next.js</h1>
  </div>
);
```

最新のNext.jsでは1行目のimport文は不要になりました。

## サーバ起動

開発版のサーバ起動は次のようにします。

```
$ npm run dev
```

その後、 http://localhost:3000/ を開きましょう。

ポート番号を指定する場合は `npm run dev -- -p 3333` とします。

## Hot code reloading

サーバを起動したままindex.jsを編集してみましょう。
ファイルを保存するとブラウザの表示が即座に反映されます。

## 課題

1. 上記の動作を確認する
2. pages直下にindex.js以外のファイルを作る
3. pages配下にフォルダを作りさらにファイルを作る
