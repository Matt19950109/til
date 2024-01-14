## プロミスチェーン

- Promiseを使用して非同期処理を順次実行すること

    function sleep(val) {
      //returnで返すことにより関数実行時にthenメソッドを使えるようにする
      return new Promise(function(resolve) {
        setTimeout(function() {
          console.log(val++);
          resolve(val);
        }, 1000);
      })
    
    }
    
    
    //ES6以降の非同期処理はPromiseを使用する
    sleep(0).then(function(val) {
      //非同期処理をつなげるためには
      //コールバック関数内でプロミスのインスタンスをセットする
      return sleep(val);
    }).then(function(val) {
      return sleep(val);
    })
