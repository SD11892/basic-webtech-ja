# presets

すでにes2015を使ったように、Babelでは複数のプラグインをまとめたプリセットがあります。

プラグインは非常に細かく数が多いので、速度がそこまで重要でなければプリセットを使う方がよいでしょう。

Babel公式プリセットとしては、次のようなプリセットがあります。

- env
- latest
- es2017
- es2016
- es2015
- react
- stage-0
- stage-2
- stage-1
- stage-3

Reactを使って開発する場合はreactプリセットを使うことになるでしょう。
latestとenvは少し特殊なプリセットです。詳細はドキュメントを参照。

### 非公式プリセット

プラグインと同様にプリセットも誰でもつくることができます。

https://www.npmjs.com/search?q=babel-preset

- airbnb
- eslatest-node6
- es2015-node

などが便利かもしれません。

## 課題

1. プリセットの中身を見てみる

## 参考情報

- https://babeljs.io/docs/plugins/#presets
