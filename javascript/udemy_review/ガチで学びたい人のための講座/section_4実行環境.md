## 4-14 javascriptの実行環境
- universal javascript…様々なソフトウェア上で動くjavascriptのこと

## 4-15 javascriptが実行されるまで
- main.js内に記載がなくても、windowオブジェクトは既に生成されている
  ※windowオブジェクトはjavascriptエンジンによって準備されている
- javascript実行前にはグローバルオブジェクトとthisが準備される
- ブラウザのグローバルオブジェクトはWindowオブジェクトとなる。

# 4-16 実行コンテキスト

- グローバルコンテキスト
  実行中のコンテキスト内の変数・関数、グローバルオブジェクト、thisの3つが使用可能
  例)index.html内で設定した「main.js」ファイル内

- 関数コンテキスト
  実行中のコンテキスト内の変数・関数、arguments,super,this,外部変数(関数の外で定義されている変数)
  
      例）
      function b() {
        console.log(this, arguments, a);
      }

# 4-17 コールスタック 
## 調査方法
検証ツール→sources→Call Stackを確認
- ctrl + Rで更新
- anonymous→グローバルオブジェクトのこと
- Last In, First Out(後入れ、先出し)

# 4-18 ホイスティング
- コンテキスト内で宣言した変数や関数の定義をコード実行前にメモリーに配置すること
- 関数宣言前にその関数を呼び出してもメモリーに保存されているため呼び出し可能
※変数(const,let)定義前に呼び出すとエラーが発生する
### undefined
- 値が未定義のこと。javascriptが持っている特殊な値
**varで変数を定義したとき**に表示される(非推奨)

### 関数宣言
    function a() {
      //処理を記述
    }

### 関数式
    const a = function(){
      //処理を記述
    }
