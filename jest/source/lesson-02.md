# 環境構築

## Node.js v6をインストール

- https://nodejs.org/en/download/

## 作業用ディレクトリを作成

```
$ mkdir jest-trial
$ cd jest-trial
```

## package.jsonを用意

```
{
  "name": "jest-trial",
  "private": true,
  "scripts": {
    "test": "jest"
  },
  "devDependencies": {
    "jest": "^19.0.2"
  },
  "jest": {
    "testEnvironment": "node"
  }
}
```

## パッケージをインストール

```
$ npm install
```
