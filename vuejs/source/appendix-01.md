# Single file componentについて

本教材では取り扱いませんが、コンポーネントは一つのファイルにHTML/JS/CSSをまとめて書くこともできます。vueファイルと呼ばれます。

例えば、下記のようになります。

`item-component.vue`ファイル

```
<template>
  <div>
    <input type="checkbox" key="item.title" :checked="item.checked" @change="toggle">
    <span :style="{ textDecoration: item.checked ? 'line-through' : 'none' }">
      {{item.title}}
    </span>
  </div>
</template>

<script>
module.exports = {
  props: ['item'],
  methods: {
    toggle: function() {
      this.$emit('toggle');
    }
  },
};
</script>

<style scoped>
input:focus {
  background-color: lightyellow;
}
</style>
```

このようにすると、テンプレートのエスケープが不要になったりプリプロセッサーを使えます。プリプロセッサーはscriptやstyleにも使えます。

大規模なアプリを開発する場合は、コンポーネントを分割して構造化することが重要になるでしょう。

## 参考情報

- https://vuejs.org/v2/guide/single-file-components.html
