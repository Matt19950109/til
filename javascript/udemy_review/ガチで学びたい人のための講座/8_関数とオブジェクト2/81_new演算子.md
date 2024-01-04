# new演算子の仕組み

- コンストラクター関数からインスタンスを作成するために使用する演算子

## コンストラクター関数の戻り値がオブジェクト
- 新しいインスタンスオブジェクトとして返す

    return{…}　→　{…}

### 以下の挙動を実施している

        function F(a, b) {
            this.a = a;
            this.b = b;
            return {};
        }
        
        F.prototype.c = function() {}
        
        //レストパラメーター
        function newOpe(C, ...args)　{
        
            //__proto__に格納された空のオブジェクトを生成する
            const _this = Object.create(C.prototype);
        
            //空のオブジェクトに引数を格納する(オブジェクトは参照を渡すため実引数にも反映される)
            const result = C.apply(_this, args);
            console.log(result, _this);

            return _this;
        } 
        
        const instance = newOpe(F, 1, 2);


## オブジェクト以外
### このオブジェクトを'this'の参照先として関数を実行
        prototype →　prototypeをコピー


