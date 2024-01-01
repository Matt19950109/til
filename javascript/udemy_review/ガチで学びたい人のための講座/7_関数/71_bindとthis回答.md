### アロー関数にthisを記述するのは適さない

    const person = {
        name: 'Tom',
        bye() {
            console.log('Bye ' + this.name);
        },
        hello: function (greeting) {
            console.log(greeting + ' ' + this.name);
            return greeting + ' ' + this.name;
        },
        /**
         * 問題４：
         * 1秒後に"hello Tom"
         * と出力されるような、メソッドを
         * personオブジェクトに追加してみてください。
         * 
         * 以下のように使用するものとします。
         * `person.hello1s()` 
         * -> 1秒後に"hello Tom"と出力
         * 
         * 3通りの方法で実装してみてください。
         * １．bind
         * ２．アロー関数
         * ３．thisを一旦変数に代入
         */
        hello1s () => {
            // setTimeout(this.hello.bind(this, 'hello'), 1000);
    
            //setTimeout(() => {
            //  this.hello('hello');
            //}, 1000)
    
            const _this = this;
            setTimeout(function() {
                _this.hello('hello');
            })
        }
        
    }
    person.hello();
