# 外部API呼び出し

外部APIを呼び出すなど非同期処理をする場合は、
class型のコンポーネントを使って制御します。

## getInitialProps

Reactを拡張した新しいライフサイクルメソッドです。
コンポーネントが最初に作られた時に呼ばれ、propsを作ります。
サーバでもクライアントでも動くコードなので注意が必要です。

staticメソッドでありasyncが指定できます。

簡単なサンプルを動かしてみましょう。

index.jsを次のようにします。

```
import React from 'react';
import Link from 'next/link';

export default class extends React.Component {
  static async getInitialProps({ req }) {
    await new Promise(cb => setTimeout(cb, 1000));
    return {
      from: req ? 'server' : 'client',
      userAgent: req ? req.headers['user-agent'] : navigator.userAgent,
    };
  }
  render() {
    return (
      <div>
        <h1>Hello Next.js</h1>
	<p>from {this.props.from}</p>
	<p>{this.props.userAgent}</p>
        <Link href="/about"><a>About</a></Link>
      </div>
    );
  }
}
```

サーバで実行された場合とサーバで実行された場合で違うことがわかります。

## isomorphic-fetch

クライアントでもサーバでも使えるfetchをインストールします。

```
$ npm install isomorphic-fetch --save
```


## API呼び出し

次のようにして為替レートのAPIを呼び出して表示します。

```
import React from 'react';
import Link from 'next/link';
import 'isomorphic-fetch';

export default class extends React.Component {
  static async getInitialProps() {
    const res = await fetch('http://api.fixer.io/latest?base=USD');
    const data = await res.json();
    return {
      rate: data.rates.JPY,
    };
  }
  render() {
    return (
      <div>
        <h1>Hello Next.js</h1>
        <p>JPY/USD = {this.props.rate}</p>
        <Link href="/about"><a>About</a></Link>
      </div>
    );
  }
}
```

## 課題

1. 上記の動作を確認する
2. API呼び出しのパラメータを変える(できれば動的に)
3. (挑戦) 他のAPIを呼び出す
