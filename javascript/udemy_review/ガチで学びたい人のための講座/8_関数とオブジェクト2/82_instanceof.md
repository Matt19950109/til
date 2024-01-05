## instanceof
- どのコンストラクターから生成されたオブジェクトかを調べる

### trueが返る

        function F(a, b) {
        this.a = a;
        this.b = b;
        }
        
        F.prototype.c = function(){}
        
        const.instance = new F(1,2)
        console,log(instance instanceof F)

### falseが返る
        function F(a, b) {
        this.a = a;
        this.b = b;
        return {a: 1};
        }
        
        F.prototype.c = function(){}
        
        const.instance = new F(1,2)
        console,log(instance instanceof F)

20行目以降の処理

        function F(a, b) {
        this.a = a;
        this.b = b;

        //ここからreturn {}ならではの処理
        const result = new Object();
        result.a = 1;
        return result;
        return {a: 1};
        }

- オブジェクトかそうでないかによって条件分岐
function fn(arg) {
  if(arg instanceof Array) {
        arg.push('value');
  } else{
        arg['key'] = 'value';
  }
  console.log(arg)
}

### オブジェクトリテラルを調べる
