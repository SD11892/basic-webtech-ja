# modules

これまでJavaScriptにはモジュールの機能が規定されず、ライブラリで実現されていました。
ES2015 modulesはそれらを置き換える標準的な仕様です。

## import

モジュールを読み込む書式です。

```
import defaultMember from "module-name";
import * as name from "module-name";
import { member } from "module-name";
import { member as alias } from "module-name";
import { member1 , member2 } from "module-name";
import { member1 , member2 as alias2 , [...] } from "module-name";
import defaultMember, { member [ , [...] ] } from "module-name";
import defaultMember, * as name from "module-name";
import "module-name";
```

## export

モジュールをエクスポートする書式です。

```
export { name1, name2, ..., nameN };
export { variable1 as name1, variable2 as name2, ..., nameN };
export let name1, name2, ..., nameN; // var も使用可
export let name1 = ..., name2 = ..., ..., nameN; // var, const も使用可

export default expression;
export default function (...) { ... } // class, function* も使用可
export default function name1(...) { ... } // class, function* も使用可
export { name1 as default, ... };

export * from ...;
export { name1, name2, ..., nameN } from ...;
export { import1 as name1, import2 as name2, ..., nameN } from ...;
```

## 注意点

- CommonJSと異なり、staticな宣言として扱われる
  - 実行時に変えることはできない
  - しかし、babelでトランスパイルするとCommonJSになるので混乱の元
  - しかも、defaultの扱いが特殊
- Node v6ではまだ実装されていない
- そもそもES2015の仕様ではモジュールをどのように読み込むかは規定されていない 

## 課題

1. (挑戦) Babelの環境を作って動作を確認する

## 参考情報

- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/import 
- https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/export 
