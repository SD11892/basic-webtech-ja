# アプリでの設定例

実際にアプリで使う場合に設定するpackage.jsonの例を載せます。
開発時は変更が多いのでbabel-nodeを使い、
本番環境では事前にコンパイルする想定です。

```
{
  "name": "sample-app",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node build/app",
    "build": "babel src -d build",
    "dev": "babel-node src/app"
  },
  "devDependencies": {
    "babel-cli": "*",
    "babel-preset-react": "*",
    "babel-preset-eslatest-node6": "*"
  },
  "babel": {
    "presets": ["react", "eslatest-node6"]
  }
}
```

この設定は `src/app.js` にメインのJSファイルを作成する想定で、
コンパイルされると `build/app.js` になります。

## 使用方法

開発時は、

```
$ npm run dev
```

で起動して、本番環境では、

```
$ npm run build
$ npm start
```

のようにビルドしてから起動します。

## 課題

1. 上記の設定で実際にコードを書いて動かしてみる

## 参考情報

- https://babeljs.io/docs/usage/babelrc/
