## Promise
非同期処理をより簡単に可読性が上がるように書いたもの

    new Promise(function(resolve, reject){
      console.log('Promise');
      resolve("hello"); //then以降の処理に移る
    
    //resolve,rejectが呼ばれるまでは実行されない
    }).then(function(data){
      console.log('then ' + data);
      return data; //引数を返却しないと次の処理にthen undefinedが表示される
    }).then(function(data){
      console.log('then ' + data);
      throw new Error(); //catchに処理が移る
    }).catch(function(){
      console.log('catch')
    }).finally(function(){ //finallyには引数を渡すことができない
      console.log('finally');
    })
    
    console.log('global end');
