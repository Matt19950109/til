## Json
- あくまで文字列なのでオブジェクトに変換を実施する場合がある
- JSONはサーバー側とやり取りするとき
- ローカルスタッフにデータを格納するとき

### JSON.stringify
    const obj = {a: 0, b: 1, c: 2};
    
    function replacer(prop, value) {
      if(value < 1) {
        return;
      }
      return value;
    }
    //オブジェくトをJSONに変換
    //第二引数に関数や配列を記述し、特定のプロパティを指定可能
    const json = JSON.stringify(obj, ["a", "b"]);
    
    //stringと表示される
    console.log(json);

### JSON.parse

        const obj = {a: 0, b: 1, c: 2};
        
        function replacer(prop, value) {
          if(value < 1) {
            return;
          }
          return value;
        }
        //オブジェくトをJSONに変換
        //第二引数に関数や配列を記述し、特定のプロパティを指定可能
        const json = JSON.stringify(obj, ["a", "b"]);
        
        //stringと表示される
        console.log(json);
        
        
        const obj2 = JSON.parse(json);
        console.log(obj2);
        
        //JSON
