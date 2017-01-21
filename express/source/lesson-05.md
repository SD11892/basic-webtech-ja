# static

これまで見てきたようにAPIとしてテキストデータやJSONデータを返す以外にも、
普通のwebサーバのようにHTMLファイルやCSSファイルを配置することもできます。

`app.js`に下記を追加します。

```
const path = require('path');

app.use(express.static(path.join(__dirname, 'public')));
```

`public`というディレクトリを作ってその中にファイルを配置します。
ディレクトリを階層化することもできます。

## 課題

- HTMLファイルを配置して、表示されるかを確認する 

## 参考情報

- http://expressjs.com/en/4x/api.html#express.static
