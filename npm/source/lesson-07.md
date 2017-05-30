# npm-run-all

複数のタスクを並行して進めたい場合があります。
`&` で接続することもできますが、終了が捕捉できないなど不都合があります。

https://github.com/mysticatea/npm-run-all

npm-run-allの `run-p` を使うと並列実行が簡単になります。

## 使用例

```
$ run-p task1 task2
```

task1, task2はnpm scriptsの名前です。

## package.jsonの例

```
{
  "scritps": {
    "test": "run-p test:*",
    "test:lint": "eslint",
    "test:flow": "flow",
    "test:jest": "jest"
  },
  "devDependencies": {
    "npm-run-all": "^4.0.2"
  }
}```

上記は抜粋ですので、他の部分は補完してください。

## 課題

- run-pの動作を確認する
- run-sやnpm-run-allのドキュメントも確認する
