# メッセージ一覧

メッセージ一覧を表示するようにする。

## queryを変更

```
const query = gql`
  query {
    allMessages {
      text
    }
  }
`;
```

## コンポーネントで表示

```
        <ul>
          { 
            (data.allMessages || []).map(({ text }) => (
              <li>{text}</li>
            ))
          }
        </ul>
```

## 課題

1. 上記をヒントに動作させる
2. (挑戦) 最新の10件だけを表示するように改造する
