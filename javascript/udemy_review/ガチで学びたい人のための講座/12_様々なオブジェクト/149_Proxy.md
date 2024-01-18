## Proxy
    - プロパティ操作に独自の処理を追加するためのオブジェクト
    
    ### コード例
    const targetObj = { a: 0 };
    const handler = {
      //トラップ(オブジェクトのプロパティに変更があった時に作動する)
      set: function(target, prop, value, receiver) {
        console.log(`[set]: ${prop}`);
    
        //以下の値の変更前に処理を加えることができる
        target[prop] = value;
    
        //値の変更を外部から阻止する
        throw new Error('cannnot add prop')
      },
      get: function(target, prop, receiver) {
        console.log(`[get]: ${prop}`);
        return target[prop]
      },
      deleteProperty: function(target, prop) {
        console.log(`[delete]: ${prop}`);
        delete target[prop];
      }
    }
    //
    const pxy = new Proxy(targetObj, handler);
    pxy.a = 1;
    pxy.a;
    delete pxy.a;
