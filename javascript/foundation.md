# javascriptの代表的な関数式

- 関数宣言<br>
  呼び出しされるコード文より後に記述しても読み込みが可能<br>
function 関数名( 引数 ){<br>
  // 関数内の処理<br>
}

- 関数式
  変数 = function( 引数 ){
    // 関数内の処理
  }

- 無名関数
  const 変数 = function(){
    // 関数内の処理
  }

- 即時関数
  関数を定義すると同時に実行される構文
  
  (function 関数名( 引数 ) {
   // 関数内の処理 
  })(1)

- アロー関数
  functionの記述の代わりに「() =>」を記述することで関数を定義する構文

  const 変数名 = () => {
  処理
  }


# 代表的な値の取得方法

- getelementbyid
  IDを取得
  
- getelementbyclass
  class名を取得
  
- queryselectorall
  指定したclassなどの値をすべて取得
