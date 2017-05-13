# fetch利用

[fetch](https://developer.mozilla.org/docs/Web/API/Fetch_API/)は新しいリソース取得のAPIでpromiseベースです。

## 準備

```
npm install isomorphic-fetch --save
```

[isomorphic-fetch](https://github.com/matthew-andrews/isomorphic-fetch)はnodeでfetchを使えるようにします。

## 例

```
const fetch = require('isomorphic-fetch');

const getFilmTitles = async () => {
  const response = await fetch('https://ghibliapi.herokuapp.com/films/');
  const films = await response.json();
  return films.map(film => film.title);
};

const main = async () => {
  const titles = await getFilmTitles();
  console.log(titles);
};
```

https://ghibliapi.herokuapp.com/ を利用しました。

## 課題

1. 上記を動作させる
2. (挑戦) 出演キャラクターの名前を取得する
