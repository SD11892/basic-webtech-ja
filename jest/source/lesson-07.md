# スナップショットテスト

テスト結果の期待値を直接書くのではなく、スナップショットとして保存しておいて、
次のテストで変化がないことを確認するテストです。

UI開発でスクリーンショットを撮って変化がないことを確認するのと同様の使い方が想定されていますが、UI開発に限定されるものではありません。

## 動作の確認

snapshot.test.jsを作成

```
test('always the same number', () => {
  const data = { number: 1234 };
  expect(data).toMatchSnapshot();
});

test('random number', () => {
  const data = { number: Math.random() };
  expect(data).toMatchSnapshot();
});
```

実行

```
$ npm test snapshot.test.js
```

一回目は成功します。生成されたスナップショットを見てみましょう。
`__snapshots__`にファイルが生成されているはずです。

再度テストを実行するとテストのうち1つが失敗します。

## Reactコンポーネント

同様のテストがReactコンポーネントについても可能です。
https://github.com/facebook/react/tree/master/packages/react-test-renderer
を使うとレンダリング結果をjsonにすることができ、
それをスナップショットとして保存します。

## ドキュメント

詳しくは、下記のドキュメントを参照しましょう。

- https://facebook.github.io/jest/docs/snapshot-testing.html

## 課題

1. 上記の動作を確認する
2. (Lesson 08終了後に)Reactコンポーネントテストを書く
