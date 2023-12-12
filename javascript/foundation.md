# データ型の種類
- **boolean** …trueもしくはfalse 
- **char** …文字
- **byte** …整数(-128～127)
- **short** …整数(-32768～32767)
- **int** …整数(-2147483～2147483647)
- **long** …整数(広範囲)
- **float** …小数(精度低)
- **double** …小数(精度高)


## javascriptの代表的な関数式

- **関数宣言**<br>
  呼び出しされるコード文より後に記述しても読み込みが可能  
function 関数名( 引数 ){<br>
  // 関数内の処理<br>
}

- **関数式**  
  変数 = function( 引数 ){<br>
    // 関数内の処理<br>
  }

- **無名関数**  
  const 変数 = function(){<br>
    // 関数内の処理<br>
  }

- **即時関数**<br>
  関数を定義すると同時に実行される構文<br>
  
  (function 関数名( 引数 ) {<br>
   // 関数内の処理 <br>
  })(1)

- **アロー関数**<br>
  functionの記述の代わりに「() =>」を記述することで関数を定義する構文<br>

  const 変数名 = () => {<br>
  処理
  }


## 代表的な値の取得方法

- **getelementbyid**<br>
  IDを取得
  
- **getelementbyclass**<br>
  class名を取得
  
- **queryselectorall**<br>
  指定したclassなどの値をすべて取得

## 代表的な演算子(javascriptならではのもの)
- **a++ または ++a** → a + 1をしてaに代入
- **a-- または --a** → a - 1をしてaに代入
