# 基本設定

- ルールを設定しないと何も有効にならない
- ルールは.eslintrcやpackage.jsonに書く
- 起動スクリプトをpackage.jsonに書く

package.jsonの例

```
{
  "scripts": {
    "lint": "eslint ."
  },
  "eslintConfig": {
    "parserOptions": {
      "ecmaVersion": 6,
      "sourceType": "module",
      "ecmaFeatures": {
        "jsx": true
      }
    },
    "rules": {
      "semi": 2
    }
  }
}
```

## ルールの例

- http://eslint.org/docs/rules/curly
- http://eslint.org/docs/rules/eqeqeq
- http://eslint.org/docs/rules/semi

## 課題

- 自分のプロジェクトに設定する

## 参考情報

- http://eslint.org/docs/user-guide/configuring
