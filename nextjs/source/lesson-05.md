# ページ遷移

next.jsでのページ遷移はserver-side renderingをサポートするため少し特殊です。

## 基本的な使い方

./pages/index.js と ./pages/about.js があるとします。

index.jsに置いて次のようにしてabout.jsへのリンクを作ります。

```
import Link from 'next/link';

export default () => (
  <div>
    <h1>Hello Next.js</h1>
    <Link href="/about"><a>About</a></Link>
  </div>
);
```

参考までにabout.jsは例えば次のようにします。

```
import Link from 'next/link';

export default () => (
  <div>
    <h1>About</h1>
    <Link href="/"><a>Index</a></Link>
  </div>
);  
```

## プリフェッチ

next.jsではcode splittingが有効なため、ページは必要になって初めて取得されます。
すなわち初めてページを表示するときはロードに少し時間がかかります。
そこで、事前に取得するプリフェッチを指定することで、事前にロードしてページの表示を速くすることができます。

```
import Link from 'next/link';

export default () => (
  <div>
    <h1>Hello Next.js</h1>
    <Link href="/about"><a>About</a></Link>
  </div>
);
```

ただし、プリフェッチはプロダクション環境でしか効きません。

## プログラムによるページ遷移

Linkコンポーネントではなくプログラムによるページ遷移もできます。

```
import Router from 'next/router';

export default () => (
  <div>
    <h1>Hello Next.js</h1>
    <button onClick={() => Router.push('/about')}>About</button>
  </div>
);
```

## 課題

1. 上記の動作を確認する
2. ボタンを押してから1秒経ってからページ遷移するようにする
3. Lesson 08が終わってからプリフェッチの動作確認をする
