# メッセージ投稿

メッセージを投稿できるようにする。

## mutation

```
const mutation = gql`
  mutation addMessage($text: String!) {
    createMessage(text: $text) {
      id
    }
  }
`;
```

## component

```
@graphql(mutation)
class GraphQLAddMessage extends React.PureComponent {
  static propTypes = {
    mutate: PropTypes.func,
  } 
  constructor() {
    super();
    this.state = { text: '' };
  } 
  render() {
    const { mutate } = this.props;
    return (
      <div>
        <h2>Add Message</h2>
        <input type="text" value={this.state.text} onChange={e => this.setState({ text: e.target.value })} />
        <button
          onClick={() => {
            mutate({ variables: { text: this.state.text } });
            this.setState({ text: '' });
          }}>
          Add
        </button>
      </div>
    );
  } 
}
```

## 課題

1. 上記をヒントに動作させる
2. (挑戦) 投稿完了のメッセージを表示する
