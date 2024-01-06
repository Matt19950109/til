## super
- 継承元の関数を呼び出すためのキーワード
- 関数コンテキスト内で使用できる

- suoerをsourcesのwatchで確認しても表示されない


        class Person {
          constructor(name, age) {
            this.name = name;
            this.age = age;  
          }
        }
      
        class Japanese extends Person {
          constructor(name, age, gender)
      
        // 継承後のコンストラクター関数宣言より前にsuperを記載する
            super(name, age);
            this.gender = gender; 
          }
        
          hello() {
          console.log('hello' + this.name);
          }
        }
        
        const taro = new Japanese('Taro', 23, 'Male')

### superはメソッドの継承も可能(後から呼び出しも可能)
super.hello()

### setPrototypeOf(オブジェクト, 継承させたいオブジェクト)
Object.setPrototypeOf(Bob, american)
