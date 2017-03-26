# Reactコンポーネントテスト

FacebookではReactのテストにJestが使われています。

## reactのインストール

本体をインストールします。

```
$ npm install --save react react-dom
```

テスト用ライブラリをインストールします。

```
$ npm install --save-dev react-test-renderer
```

他にもDOMのテストにTestUtilsやEnzymeを使うこともあります。

## babelの導入

Reactを使うにはbabelの設定をする必要があります。

```
$ npm install --save-dev babel-jest babel-preset-es2015 babel-preset-react
```

pakcage.jsonにbabelの設定を追記します。

```
{
  "babel": {
    "presets": ["es2015", "react"]
  }
}
```

## コンポーネントのソースコード

src/Hello.jsx

```
import React from 'react';

export default () => (
  <div>
    <h1>Hello</h1>
  </div>
);
```

## コンポーネントのソースコード

src/Hello.text.jsx

```
import React from 'react';
import renderer from 'react-test-renderer';

import Hello from './Hello';

describe('Hello component', () => {
  it('should match snapshot', () => {
    const component = renderer.create(<Hello />);
    const tree = component.toJSON();
    expect(tree).toMatchSnapshot();
  });
});
```

## テスト実行

```
$ npm test src/Hello.text.jsx
```

## ドキュメント

詳しくは、下記のドキュメントを参照しましょう。

- https://facebook.github.io/jest/docs/tutorial-react.html

## 課題

1. 上記の動作を確認する
