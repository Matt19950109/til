## setとget
- ディスクリプタのオプションで設定できる値
- なんらかの処理を間に挟む際に使用する

### javaの使用時によく使われる

## 記述
    function Person1(name, age) {
      this._name = name;
      this._age = age;
    }
    
    Object.defineProperty(Person1.prototype, 'name', {
      get: function() {
        return this._name;
      },
      set: function() {
      this._name = val;
      }
    });
    
    const p1 = new Person1

## クラスを用いた場合
class Person2 {
    constructor(name, age) {
        this._name = name;
        this._age = age;
    }

    get name() {
        console.log('hello')
        return this._name;
    }
    
    set name(val) {
        this._name = val;
    }

    static hello() {
    console.log('hello')
    }
}

    Person2.hello()

## スタティックメソッド
- インスタンス化を必要としないメソッド
