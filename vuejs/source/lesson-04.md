# イベント処理

各アイテムにチェックボックスをつける。

データを次のようにします。

```
const items = [{
  title: 'orange',
  checked: false,
}, {
  title: 'apple',
  checked: false,
}, {
  title: 'grape',
  checked: false,
}];
```

チェックボックスを表示するためにHTMLを次のようにします。

```
<div id="app">
  <h1>Items</h1>
  <ul>
    <li v-for="item in items">
      <input type="checkbox" v-model="item.checked">
      {{item.title}}
    </li>
  </ul>
</div>
```

これで、`checked`というプロパティにチェックボックスの値が入るようになりました。

全てをチェックするボタンを追加してみます。

```
<button @click="items.forEach(item => { item.checked = true; })">
  check all
</button>
```

チェックされている個数を表示させます。

```
new Vue({  
  el: '#app',
  data: { items },
  computed: {
    checkedCount: function() {
      return this.items.filter(item => item.checked).length;
    }
  },
});
```

HTMLは例えば次のように変更しましょう。

```
<h1>Items ({{checkedCount}})</h1>
```

## 課題

1. 上記を動作させる (コンソールでもitemsを確認する)
2. 全てチェックを外すボタンを追加する
3. (挑戦) `@click`の中身をmethodsで定義する

## 参考情報

- https://vuejs.org/v2/guide/forms.html
- https://vuejs.org/v2/guide/events.html
- https://vuejs.org/v2/guide/computed.html
