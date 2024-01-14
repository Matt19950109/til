## Promise
- 並列処理においては格納されたすべての処理が完了するまでは次のthenメソッドには移らない

        function sleep(val) {
          return new Promise(function(resolve) {
            setTimeout(function() {
              console.log(val++);
              resolve(val);
            }, val * 500);
          });
        }
        
        //配列に格納されたPromiseインスタンスをすべて実施。
        //全ての完了を待ってからthenメソッドに移る
        Promise.all([sleep(2), sleep(3), sleep(4)])
        .then(function(data) {
          //resolve内(5行目)の引数を渡すことができる
          //今回の引数(data)は3,4,5を配列で渡す
          console.log(data);
        });
        
        
        
        sleep(0).then(function(val) {
          return Promise.all([sleep(2), sleep(3), sleep(4)]);
        }).then(function(val) {
          console.log(val);
          return sleep(val);
        }).then(function(val) {
          return sleep(val);
        })


## raceメソッド
- 配列内のどれか一つが完了した時点で次の処理に移行する

### コード例
        Promise.race([sleep(2), sleep(3), sleep(4)])
        .then(function() {
          console.log(data);
        })
