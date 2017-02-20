# 入力フォーム

リストにアイテムを追加できるようにする。

HTMLに次を追加します。

```
<form @submit.prevent="items.push({ title: newTitle, checked: false })">
  <input v-model="newTitle">
</form>
```

`.prevent`をつけないと画面が更新されてしまい、期待通りに動きません。

JSを次のようにします。

```
new Vue({ 
  el: '#app',
  data: { items, newTitle: '' },
});
```

これで、フォームから新しいアイテムを追加できるようになりました。

## 課題

1. 上記を動作させる (コンソールでもitemsを確認する)
2. `description`フィールドも作る、submitボタンも作る
3. 処理後にテキストフィールドを空にする
4. (挑戦) `@submit`の中身をmethodsで定義する
5. (挑戦) アイテムの削除機能を作る

## 参考情報

- https://vuejs.org/v2/guide/events.html
- https://vuejs.org/v2/api/#methods
