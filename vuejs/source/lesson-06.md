# スタイル変更

チェックがついたものに横線を入れてみましょう。

HTMLの該当部分を次のように変更します。

```
<span :style="{ textDecoration: item.checked ? 'line-through' : 'none' }">
  {{item.title}}
</span>
```

## 課題

1. 上記の動作を確認する
2. cssを定義して`:class`を使って表示を変えてみる

## 参考情報

- https://vuejs.org/v2/guide/class-and-style.html 
