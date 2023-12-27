## 即時関数
関数定義と同時に一度だけ実行される関数  
※実行結果が呼び出し元に返却される

- 無名関数
  
      (function (){
        //処理を記述
      })();
- 関数スコープの内外で使用したい変数や関数を明確に使い分けたいときに使用することがある
## javascriptにおいて()の用途
- 関数の実行
- グループ化

### クロージャー
- 関数とその外側の設定した変数との関係を表す概念。  
  関数内部の関数を外部から使えるようにしてしまう記法の一つ
- 加算ができている例
      function incrementFactory() {
          
          let num = 0;
      
          function a() {
              num = num + 1;
              console.log(num);
          }
      
          return a;
      }
      
      const increment = incrementFactory();    
      increment();
      increment();
      increment();
      increment();

- よくない例

    ×この記述法だと数は積み重ねされない
    function incrementFactory() {
        
        let num = 0;
    
        function a() {
            num = num + 1;
            console.log(num);
        }
    
        return a;
    }
    
    incrementFactory();
    incrementFactory();
    incrementFactory();
