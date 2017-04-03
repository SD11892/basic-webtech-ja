# jest.mockの実例

## テスト対象コード

src/load-raw-data.js

```
import fetch from 'isomorphic-fetch'; 

export defualt () => fetch('http://api.fixer.io/latest?base=USD');
```

src/load-data.js

```
import loadRawData from './load-raw-data';

export default () => loadRawData().then(res => res.json());
```

## 通常のテストコード

src/load-data.test.js

```
import loadData from './load-data';

test('normal', () => {
  return loadData().then((data) => {
    expect(data).toMatchObject({ base: 'USD'  });
  }); 
});
```

これだとネットワーク通信が発生してしまいます。

## jest.mockを使ったテストコード

src/load-data.test.js

```
import loadData from './load-data';

jest.mock('./load-raw-data', () => {
  const dummyRes = {
    json: () => ({ base: 'USD' }),
  };
  return jest.fn(() => Promise.resolve(dummyRes));
});

test('mocked', () => {
  return loadData().then((data) => {
    expect(data).toMatchObject({ base: 'USD' });
  });
});
```
