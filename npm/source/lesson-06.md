# shelljs/shx

npm scriptsを使う上で、 `&&` や `||` は役に立ちます。
unixつまりLinuxやOSXでは書き方は同じです。
これはWindowsでも動きます。しかし、 `;` は使えません。　
`rm` もWindowsでは使えません。

grunt/gulpたちの強みの一つとしてOS非依存がありましたが、
npm scriptsが好きなあなたにはshelljsがおすすめです。

http://shelljs.org/

shelljsはunixのshellコマンドをnodeで実装したものです。
もちろん全てが実装されているわけではありませんが、よく使うものが用意されています。
shxはshelljsのCLIラッパーです。

## shxの使用例

例えば、buildというディレクトリを消す場合、

```
$ rm -rf build
```

としているところを、

```
$ shx rm -rf build
```

のようにするだけです。shxへのパスは通っている必要があります。
npm scriptsに書く場合は `./node_modules/.bin` にパスが通りますので簡単です。

## package.jsonの例

```
{
  "scripts": {
    "clean": "shx rm -rf build"
  },
  "devDependencies": {
    "shx": "^0.2.2"
  }
}
```

上記は抜粋ですので、他の部分は補完してください。

## 課題

- shxの動作を確認する
