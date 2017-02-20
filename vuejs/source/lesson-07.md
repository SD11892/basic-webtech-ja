# コンポーネント化

コンポーネントとして部品化することができます。
構造化できるのでメンテナンス性が上がることが期待されます。

アイテム表示の機能をコンポーネントとして定義してみます。

```
Vue.component('item-component', {
  template: '<div><input type="checkbox" key="item.title" v-model="item.checked"><span :style="{ textDecoration: item.checked ? \'line-through\' : \'none\' }">{{item.title}}</span></div>',
  props: ['item'],
});
```

`template`はこのコンポーネントが提供するHTMLテンプレートで、
`props`はこのテンプレートが入力として受け取るプロパティです。

これを使うにはHTMLを次のようにします。

```
<li v-for="item in items">
  <item-component :item="item" />
</li>
```

`:item`でプロパティを渡しています。
これでテンプレートを使って動かすことができました。

ところで、コンポーネントはone-way data flowが基本なので、v-modelを使うのは好ましくないかもしれません。

そこで、明示的にイベント通知する仕組みでコンポーネントを書いてみます。

```
Vue.component('item-component', {
  template: '<div><input type="checkbox" key="item.title" :checked="item.checked" @change="toggle"><span :style="{ textDecoration: item.checked ? \'line-through\' : \'none\' }">{{item.title}}</span></div>',
  props: ['item'],
  methods: {
    toggle: function() {
      this.$emit('toggle');
    }
  },
});
```

v-modelではなく`:checked`すなわち`v-bind:checked`でチェックボックスの状態を入力しています。
一方、変更時は`@change`すなわち`v-on:change`で検知してtoggleイベントを発行しています。

このコンポーネントを使う場合はHTMLを次のようにします。

```
<li v-for="item in items">
  <item-component :item="item" @toggle="item.checked = !item.checked"/>
</li>
```

`@toggle`すなわち`v-on:change`でtoggleイベントのイベントハンドラを指定して値を変更しています。

(備考) この例はコンポーネントの学習としては適さないかもしれません。詳しくは公式ガイドを参照しましょう。

## 課題

1. 上記の動作を確認する
2. (挑戦) コンポーネントにさらに機能を追加してみる

## 参考情報

- https://vuejs.org/v2/guide/components.html
