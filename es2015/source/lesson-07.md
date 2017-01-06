# template literal

文字列を作るための新しい記法です。

## 複数行

```
const str = `aaa
bbb
ccc`;
const html = `
<html>
  <body>
    <h1>Hello</h1>
  </body>
</html>
`;
```

## 式展開

```
const x = 1;
const str = `x=${x}`;
const str2 = `double x is ${x * 2}`;
```

## 課題

1. テンプレートリテラルの動作を確認する

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/template_strings
