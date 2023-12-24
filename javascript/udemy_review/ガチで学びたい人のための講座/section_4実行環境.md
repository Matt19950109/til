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

- 関数コンテキスト
  実行中のコンテキスト内の変数・関数、arguments,super,this,外部変数
