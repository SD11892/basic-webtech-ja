# リスト表示

はじめにリスト型のデータ構造を表示させます。

```
const items = [{
  title: 'orange',
}, {
  title: 'apple',
}, {
  title: 'grape',
}];
```

というデータをJavaScriptタブに用意します。

HTML側は次のようにします。scriptタグは残してください。

```
<div id="app">
  <h1>Items</h1>
  <ul>
    <li v-for="item in items">{{item.title}}</li>
  </ul>
</div>
```

JSタブには次を追加します。

```
new Vue({
  el: '#app',
  data: { items },
});
```

表示を確認しましょう。

## 課題

1. 上記を動作させる
2. titleに加えてdescriptionフィールドも追加する
3. (挑戦) コンソールでitemsにデータを追加する 

## 参考情報

- https://vuejs.org/v2/guide/list.html
- https://vuejs.org/v2/api/#v-for
