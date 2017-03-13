# スタイル

next.jsではこれまでのcssとできるだけ同じように使ってスタイル指定をする仕組みを使っています。

## styled-jsx

このライブラリを使うと、jsxにcssが埋め込めるようになります。

```
import React from 'react';

export default () => (
  <div>
    <h1>Hello Next.js</h1>
    <style jsx>{`
      h1 {
        color: red;
      }
    `}</style>
  </div>
);
```

上記のスタイル設定はコンポーネントのみで有効であり、他のコンポーネントには影響しません。

詳しい使い方は、ドキュメントを参照しましょう。

https://github.com/zeit/styled-jsx

## inline styles

React本来のスタイル設定もできます。下記はinline stylesで書いた場合です。

```
import React from 'react';

export default () => (
  <div>
    <h1 style={{ color: 'red' }}>Hello Next.js</h1>
  </div>
);
```

その他React用の様々なスタイル設定ライブラリが使用できるはずです。

## 課題

1. 上記の動作を確認する
2. スタイルを変更する
