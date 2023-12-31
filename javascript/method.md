# メソッド基礎

- **mainメソッド**  
  ①ファイルを実行すると必ずmainメソッドが実行される    
  ②mainメソッドの引数などは必ず決められた通りに記述する
  <br>
  例)
  public static voif main (String[] args){  
  }

- **メソッドの使用(引数なし)**  
  アクセス修飾子&emsp;static修飾子&emsp;返り値のデータ型&emsp;メソッド名(){  
  //  処理を記述  
  }

- **メソッドの使用(引数あり)**
  ※以下のように仮引数のデータ型を明記する必要がある  
    public&emsp;static&emsp;int&emsp;square(**int&emsp;number**){  
  //  処理を記述  
  }

①返り値のデータ型を指定する必要がある  
例)  
&emsp;public&emsp;static&emsp;**int**&emsp;returnNumber(){  
&emsp;&emsp;return 〇;  
&emsp;}  
②引数がないメソッドでも定義時の()は省略できない  

③Rubyの「def」「end」の代用で{}を使用して処理の記述を囲む

## 修飾子(クラス・メソッド・変数などの定義時に特定の機能を付加させるもの)
- **アクセス修飾子**  
  外部への公開範囲を設定する(public、protected、private)  
  
- **static修飾子**  
  状態が変化しないこと(クラスメソッド)  
  **※staticを付与しない場合はインスタンスメソッドとして定義する**
