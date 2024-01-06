## Symbol
- プロパティの重複を避けるため必ず一意の値を返す関数
- コンストラクター関数とは異なり、new演算子を用いない
- Symbolはブラケット記法[]で追加する

### ビルトインオブジェクトの拡張(あまり開発者に好まれない)
        const s = Symbol('hello');
        const s2 = Symbol('hello');
        console.log(s === s2)　→ falseを返却する
        console.log(typeof s); → symbolの型を返却する
        
        const str = new String('Tom');
        console.log(str);
        
        String.prototype[s] = function() {
            return 'hello ' + this;
        }
        
        const tom = 'Tom';
        console.log(tom[s]());

### プロトタイプ汚染
- スクリプトにより独自でprototypeのメソッドを増やして拡張すること
