# 環境構築

## Node.js v6をインストール

- https://nodejs.org/en/download/

## 作業用ディレクトリを作成

```
$ mkdir nextjs-trial
$ cd nextjs-trial
```

## package.jsonを用意

```
{
  "name": "nextjs-trial",
  "private": true,
  "scripts": {
    "dev": "next",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "^2.0.0-beta.33",
    "react": "^15.4.2",
    "react-dom": "^15.4.2"
  }
}
```

## パッケージをインストール

```
$ npm install
```
