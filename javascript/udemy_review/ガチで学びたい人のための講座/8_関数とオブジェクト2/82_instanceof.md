## instanceof
- どのコンストラクターから生成されたオブジェクトかを調べる

        function F(a, b) {
        this.a = a;
        this.b = b;
        // return {a: 1};
        }
        
        F.prototype.c = function(){}
        
        const.instance = new F(1,2)
        console,log(instance instanceof F)

### オブジェクトリテラルを調べる
