# dependenciesの書き方

依存パッケージを書く項目は何種類かあります。

- dependencies: 通常の依存パッケージ
- devDependencies: 他のパッケージから利用される場合にはインストールされないパッケージ
- peerDependencies: 直接はインストールされないが依存するパッケージ
- bundledDependencies: npm packでtgzに固めるときに一緒に入れるパッケージ、配列で名前だけ表記する
- optionalDependencies: dependenciesとほぼ同じだが、インストールに失敗しても無視される

## バージョン指定の方法

様々な方法があるが、よく使うのは下記です。

- 1.0.0
- ^1.0.0
- ~1.0.0
- >=1.0.0
- dai-shi/es-beautifier#master
- git://github.com/dai-shi/es-beautifier.git#master
- https://github.com/dai-shi/es-beautifier/archive/master.tar.gz

## 参考情報

- https://docs.npmjs.com/files/package.json#dependencies
