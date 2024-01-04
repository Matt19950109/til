## プロトタイプ

- オブジェクトに存在する特別なプロパティ  
インスタンス化した際にはprototypeの参照が__proto__にコピーされる

### インスタンス化した際の参照としてコピーされるためメモリの効率化ができる

    functtion Person(name, age) {
      this.name = name;
      this.age = age;
    }
    
    Person.prototype.hello = function() {
      console.log('hello ' + this.name)
    }
    
    const bob = new Person('Bob', 23)
    
    bob.hello()
