

        function Person(name, age) {
        this.name = name;
        this.age = age;
        }
        
        Object.prototype.hello = function() {
        console.log('Object: hello ' + this.name);
        }
        
        const bob = new Person('Bob', 18)
        
        const result = bob.hasOwnProperty('hello')
        
        //falseが返る
        console.log(result)
        
        //trueが返る
        console.log('hello' in bob);
