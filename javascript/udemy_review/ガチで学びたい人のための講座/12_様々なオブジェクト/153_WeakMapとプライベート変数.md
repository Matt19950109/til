## コード例

### person.js
    const wm = new WeakMap();
    
    export class Person {
        constructor(name) {
            // this._name = name;
    
            //wmはエクスポートされていないため外部からのアクセスを制限する
            wm.set(this, {
                name
            })
        }
    
        hello() {
            console.log(`hello ${wm.get(this).name}`);
        }
    }

### main.js
    import { Person } from './person.js';
    
    const tim = new Person('Tim', 23);
    tim.hello();
