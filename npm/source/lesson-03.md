# package.jsonの基本

package.jsonはnpmコマンドおよびnpmjs.comのための情報を含むファイルですが、
他のツールやサイトでも使う情報も含みます。
例えば、babelの設定を.babelrcの代わりに書くこともできます。
まずは標準的なpackage.jsonについて学びましょう。

## 設定項目

- name: パッケージの名前、インストールするためには必須
- version: パッケージのバージョン、インストールするためには必須
- private: 公開しないパッケージの場合は `true` にすると間違って公開してしまうことを防げる
- description, keywords, homepage, bugs, repository: 追加情報、npmjs.comで掲載されるのに使われる
- license: パッケージのライセンス、公開しない場合は `"UNLICENSED"`
- author, contributors: 作者に関する情報
- files: このパッケージを公開するとき含めるファイル、.npmignoreというファイルで不要なファイルを明示することもできる
- main: パッケージをライブラリとしてロードするときのファイル、省略するとindex.js
- bin: パッケージをCLIとして使うときのファイル
- dependencies: (次のレッスンで)
- scripts: (次のレッスンで)
- engines: nodeやnpmのバージョン指定

## 参考情報

- https://docs.npmjs.com/files/package.json
