# 環境構築

## mongodb serverをインストール

- https://docs.mongodb.com/manual/installation/

## Node.js v6をインストール

- https://nodejs.org/en/download/

## 作業用ディレクトリを作成

```
$ mkdir mongodb-trial
$ cd mongodb-trial
```

## package.jsonを用意

```
{
  "name": "mongodb-trial",
  "private": true,
  "dependencies": {
    "mongodb": "^2.2.25"
  }
}
```

## パッケージをインストール

```
$ npm install
```
