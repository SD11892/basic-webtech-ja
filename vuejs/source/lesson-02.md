# 環境構築

http://codepen.io/pen/ を使います。

## JavaScriptの設定

SettingsのJavaScriptで、JavaScript PreprocessorをBabelにする。

## ライブラリの設定

HTMLに下記を追加する。

```
<script src="https://unpkg.com/vue/dist/vue.js"></script>
```

## 動作確認

HTMLにさらに下記を追加する。

```
<div id="app">{{ message }}</div>
```

JavaScriptに下記を追加する。

```
var app = new Vue({
  el: '#app',
  data: { message: 'Hello Vue!' }
});
```

メッセージが表示されることを確認する。
