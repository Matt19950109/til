## 配列とArrayListについて


## 配列
- javaの配列は**事前に要素数を決める必要**があり、後で変更不可

①配列の宣言を行う  
　int[ ] scores ;

②配列の要素を作成。配列に代入  
  scores = new int[3];

③配列の要素を値に代入    
 scores[0] = 1 ;

### 型推論を使用する方法  
var scores = new int[3]  

※事前に格納する値が決まっている場合は以下のように配列の宣言と値の代入を同時に行うことも可能  
int [3] scores = {1, 5, 10};

## ArrayList

- リスト…Rubyの配列に似たデータ管理の仕組み
- ArrayList…可変長配列を使用するための仕組み

①ライブラリをインポート  
　import java.util.ArrayList  

②ArrayListの宣言を行う  
　ArrayList<データ型> scores = new ArrayList <データ型>　();

③ArrayListに値を代入  
  scores.add(1);

④ArrayListから要素を取り出す  
  scores.get(0);
