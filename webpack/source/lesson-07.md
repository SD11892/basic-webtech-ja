# watch

ファイルを変更するたびにビルドスクリプトを実行するのは手間かもしれません。
そこでwatch modeを使います。watch modeでは変更があったファイルだけ再ビルドされます。

## 設定

package.jsonに例えば次のように書きます。

```
{
  "scripts": {
    "webpack-watch": "webpack -w"
  }
}
```

もしくは、webpack.config.jsに次のように書きます。

```
{
  watch: true
}
```

`watchOptions`でチェック間隔なども指定可能です。

## 動作確認

watch modeでwebpackを実行してから、ファイルを編集してみましょう。

## 課題

1. 上記の動作を確認する

## 参考情報

- https://webpack.js.org/configuration/watch/
