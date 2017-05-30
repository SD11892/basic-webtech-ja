# wait-on

タスクを並列動作させる場合、一つのタスクが他のもう一つのタスクの準備完了を待つようにしたいことがあります。
例えば、apiテストをする場合サーバが立ち上がってから、テストシナリオを走らせるようにしたいでしょう。

https://github.com/jeffbski/wait-on

wait-onはfile/port/socket/httpの状態を待つクロスプラットフォームのツールです。

## 使用例

```
$ (wait-on foo.txt && echo foo) &
$ touch foo.txt
```

## package.jsonの例

```
{
  "scripts": {
    "test:api": "run-p test:api:*",
    "test:api:start-server": "PORT=8080 node server",
    "test:api:run-scenario": "wait-on http://localhost:8080/ && npm run mocha"
  },
  "devDependencies": {
    "npm-run-all": "^4.0.2",
    "wait-on": "^2.0.2"
  }
}
```

上記は抜粋ですので、他の部分は補完してください。

## 課題

- wait-onの動作を確認する
