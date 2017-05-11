# 環境構築

## Node.js v6をインストール

- https://nodejs.org/en/download/

## 作業用ディレクトリを作成

```
$ mkdir asyncawait-trial
$ cd asyncawait-trial
```

## package.jsonを用意

```
{
  "name": "asyncawait-trial",
  "private": true,
  "devDependencies": {
    "babel-cli": "^6.24.1",
    "babel-plugin-transform-async-to-generator": "^6.24.1"
  },
  "babel": {
    "plugins": [
      "transform-async-to-generator"
    ]
  }
}

```

## パッケージをインストール

```
$ npm install
```
