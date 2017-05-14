# Promise.all

async/awaitを普通に使うと非同期であるものの逐次的な処理になります。
並列処理をしたい場合はPromise.allを使います。

## 手動で展開したコード

```
const fetch = require('isomorphic-fetch');

const getFilmTitle = async (id) => {
  const response = await fetch(`https://ghibliapi.herokuapp.com/films/${id}`);
  const film = await response.json();
  return film.title;
};

const main = async () => {
  const title1 = await getFilmTitle('58611129-2dbc-4a81-a72f-77ddfc1b1b49');
  console.log(title1);
  const title2 = await getFilmTitle('ea660b10-85c4-4ae3-8a5f-41cea3648e3e');
  console.log(title2);
  const title3 = await getFilmTitle('0440483e-ca0e-4120-8c50-4c8cd9b965d6');
  console.log(title3);
};
```

## Promise.allを使った場合

```
const main = async () => {
  const titles = await Promise.all([
    getFilmTitle('58611129-2dbc-4a81-a72f-77ddfc1b1b49'),
    getFilmTitle('ea660b10-85c4-4ae3-8a5f-41cea3648e3e'),
    getFilmTitle('0440483e-ca0e-4120-8c50-4c8cd9b965d6'),
  ]);
  console.log(titles);
};
```

## さらにmapを使った例

```
const main = async () => {
  const ids = [
    '58611129-2dbc-4a81-a72f-77ddfc1b1b49',
    'ea660b10-85c4-4ae3-8a5f-41cea3648e3e',
    '0440483e-ca0e-4120-8c50-4c8cd9b965d6',
  ];
  const titles = await Promise.all(ids.map(getFilmTitle));
  console.log(titles);
};
```

## 課題

1. 上記を動作させる
2. (挑戦) ある映画の出演キャラクターの名前リストを取得する
