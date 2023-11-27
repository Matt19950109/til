# JavascriptとECMAscript

- **ECMAscript**
  プログラミング言語。javascript言語のコア部分を維持した仕様にしつつ、ブラウザ間で使用を統一したもの

## ES5とES6の違い
- **ES5** 2009年の第5版
- **ES6** 2015年の第6版

## 実行環境
- Universal Javascript 様々な環境で動けるように作成されたJavascriptのコード

- javascriptはjavascriptエンジン上で実行される
- シェアNo.1はV8とされている
- javascriptからWebAPIを通じてブラウザの操作をする

## コードが実行される前

- **グローバルオブジェクト**　JSエンジンによって生成されるコード内のどこからでもアクセスでできるオブジェクト
- **ウィンドウオブジェクト**　javascriptによって用意されているrubyでいうメソッドのようなもの  
  例)alert、documentなど

## 実行コンテキスト(コードを実行するときの文脈・状況のこと)
- グローバルコンテキスト
- 関数コンテキスト
