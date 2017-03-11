# 画像ファイルとhead

画像ファイルなどのコンテンツを使うには `static` というフォルダを作ってそこにファイルを置きます。

例えば、 `static/logo.png` というファイルを置いたとすると、
index.jsを次のようにすると画像が表示されます。

```
export default () => (
  <div>
    <h1>Hello Next.js</h1>
    <img src="/static/logo.png" />
  </div>
);
```

headは特別なコンポーネントを使って設定します。

```
import Head from 'next/head';

export default () => (
  <div>
    <Head>
      <title>Next.js Trial</title>
    </Head>
    <h1>Hello Next.js</h1>
    <img src="/static/logo.png" />
  </div>
);
```

このHeadはこのコンポーネントに入るものではなくページ全体のheadタグに動的に入るものです。
DevToolsでDOMを確認しましょう。

## 課題

1. 画像ファイルを置いて表示させる
2. headにタイトルを設定する
3. 画像ファイル以外のコンテンツを置く
4. headに他のタグも追加する
