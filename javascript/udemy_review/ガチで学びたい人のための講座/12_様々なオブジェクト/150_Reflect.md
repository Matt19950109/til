## Reflect

- JSエンジンの内部の汎用的な関数を呼び出すメソッドが格納されているオブジェクト

- 内部メソッドを呼び出す関数の格納場所
- Proxyと合わせて使用するため

        class C {
          constructor(a, b) {
            this.a = a;
            this.b = b;
          }
        }
        
        const obj1 = new C(1, 2);
        console.log(obj1);
        
        //上記の演算子を記述せずにインスタンス化を可能にする
        const obj2 = Reflect.construct(C, [1, 2]);
        console.log(obj2);

### Reflect.has
        //以下の2行は同じ結果が返ってくる（コールバック関数利用時などはReflectを使う）
        console.log('c' in obj1);
        console.log(Reflect.has(obj1, 'c'))
