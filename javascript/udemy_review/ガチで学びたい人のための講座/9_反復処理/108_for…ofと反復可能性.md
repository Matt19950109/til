## for…of

- イテレーターを持つオブジェクトの反復操作を実施

## イテレーター
- 反復操作を行う際に使用するオブジェクト  
  例）String,Array,Map,Set,argumentsなど

## Symbol(Symbol.iterator)
- 特殊なプロパティ(for…ofの実行時に使用する)

## 参考コード
    const arry = ['a', 'b', 'c'];
    
    //a,b,c,undefined,eを出力
    arry[4] = 'e'
    
    //for…ofの反復では表示されない
    Object.prototype.method = function() {}
    
    //enumerableの設定をfalseにしても14～16行目にaの値は表示される
    Object.defineProperty(arry, 0, {
      enumerable: false
    });
    
    for(let v of arry) {
      console.log(v);
    }
