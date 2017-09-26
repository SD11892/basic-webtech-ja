# プリセット設定

eslintのルールは多いので、
自分で好きなようにカスタマイズすることができますが、
すでに作られた設定を使う方が簡単です。
そこからカスタマイズすることも可能です。

有名なプリセット設定たち

- "eslint:recommended"
  - eslintに標準で提供されるrecommended設定
  - 最小限のものがまとめられている感じ
- eslint-config-airbnb
  - https://www.npmjs.com/package/eslint-config-airbnb
  - airbnb javascript style guideに沿った設定
  - だいぶ統制されたルールセット
- standard
  - http://standardjs.com
  - eslintを設定ごと内包している (設定だけのパッケージもある)
  - ルールをカスタマイズしないことが大前提
- eslint-config-google
  - https://www.npmjs.com/package/eslint-config-google
  - google javascript style guideに沿った設定

## 課題

- 好みのプリセット設定を導入して動作を確認する

## 参考情報

- http://eslint.org
