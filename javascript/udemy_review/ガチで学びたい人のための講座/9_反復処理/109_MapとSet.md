## MapとSet(コレクション)
- データを管理するための入れ物
- ES6から導入されたもの

## コード例
    //Mapオブジェクトを生成
    const map = new Map();
    
    //変数にオブジェクトを格納
    const key1 = {};
    
    //key1はオブジェクトの参照を保持しているので
    //console.log(map.get{})という記述だと新たにオブジェクトが生成されるため参照することはできない
    map.set(key1, 'value1');
    console.log(map.get(key1))
    
    const key2 = function(){}
    map.set(key2, 'value2')
    console.log(map.get(key2))
    
    let key3;
    map.set(key3 = 0, 'value3')
    console.log(map.get(key3))
    
    for(const m of map) {
      //配列でキーと値が取得できる
      //分割代入でそれぞれキーと値を取得可能
      //for inでの取得は負荷
      //[[Entries]]という特殊な格納場所に入っている
      console.log(m);
    }
    
    
    //Setをインスタンス化
    const s = new Set();
    
    
    //重複したオブジェクトは表示されない
    s.add(key1);
    s.add(key2);
    s.add(key3);
    
    //Setは添字を利用できないので以下のコードで配列に戻すことがある
    const arry = Array.from(s);
    //別海
    const arry = [...s];
    console.log(arry);
    
    for(let k of s) {
      console.log(k);
    }
