# 環境構築

## Node.js v6をインストール

- https://nodejs.org/en/download/

## 作業用ディレクトリを作成

```
$ mkdir flow-trial
$ cd flow-trial
```

## package.jsonを用意

```
{
  "name": "flow-trial",
  "private": true,
  "scripts": {
    "flow": "flow"
  },
  "devDependencies": {
    "flow-bin": "^0.44.0"
  }
}
```

## パッケージをインストール

```
$ npm install
```

## flow設定の初期化

```
$ npm run flow init
```
