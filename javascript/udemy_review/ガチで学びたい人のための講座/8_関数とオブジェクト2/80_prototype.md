## プロトタイプ

- オブジェクトに存在する特別なプロパティ  
インスタンス化した際には**prototypeの参照**が__proto__にコピーされる

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

### 以下の実装でも挙動は変わらないがメモリの容量が多くなってしまう
    functtion Person(name, age) {
      this.name = name;
      this.age = age;
      this.hello = function() {
      console.log('hello ' + this.name)
      }
    }
    
    Person.prototype.hello = function() {
      console.log('hello ' + this.name)
    }
    
    const bob = new Person('Bob', 23)
    
    bob.hello()
