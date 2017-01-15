# REPLでコーディング

REPLを使って対話的にコーディングすることができます。

例えば、CSVデータを集計するコードを書いてみましょう。

```
> dsum = data => data.reduce(countUp, {})
[Function: dsum]
> countUp = (obj, [key, val]) => Object.assign(obj, { [key]: (obj[key] || 0) + val })
[Function: countUp]
> o={}
{}
> countUp(o,['a',1])
{ a: 1 }
> countUp(o,['a',1])
{ a: 2 }
> countUp(o,['b',1])
{ a: 2, b: 1 }
> dsum([['aaa',10],['bbb',20],['aaa',3],['bbb',1]])
{ aaa: 13, bbb: 21 }
> sumCSV = text => dsum(parseCSV(text))
[Function: sumCSV]
> parseCSV = text => text.split('\n').map(line => line.split(','))
[Function: parseCSV]
> parseCSV('aaa,10\nbbb,20\naaa,3\nbbb,1\n')
[ [ 'aaa', '10' ],
  [ 'bbb', '20' ],
  [ 'aaa', '3' ],
  [ 'bbb', '1' ],
  [ '' ] ]
> sumCSV('aaa,10\nbbb,20\naaa,3\nbbb,1\n')
{ aaa: '0103', bbb: '0201', '': NaN }
```

## ファイルの読み込み

さすがに規模が少しでも大きくなってくるとREPLだけではつらいです。
そこでファイルにコードを書いて読み込むようにしましょう。

例えば、`file.js`に

```
dsum = data => data.reduce(countUp, {});
countUp = (obj, [key, val]) => Object.assign(obj, { [key]: (obj[key] || 0) + val });
```

と書いたとすると、

```
$ node file.js
```

のようにファイルを指定してnodeを起動すると最初にそのファイルが読み込まれます。

## パッケージの利用

node.jsやnpmのパッケージも使うことができます。

```
> fs = require('fs')
```

また例えば、https://www.npmjs.com/package/csv がインストールされているとすると、

```
> csv = require('csv')
```

とできます。

## 課題

- 試しにREPLで何かコーディングしてみる

## 参考情報

- https://en.wikipedia.org/wiki/Exploratory_programming 
- https://en.wikipedia.org/wiki/Read–eval–print_lo
