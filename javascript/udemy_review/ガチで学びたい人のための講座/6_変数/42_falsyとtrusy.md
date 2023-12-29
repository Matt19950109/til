### NaN
Not a Numberの略。  
**数値として期待された値が数値として返せない場合に表示される**

# AND条件とOR条件

## AND条件
- &&を用いる  
  各変数を評価を実施。falsyの値が来たらそれを表示。  
  指定した変数がすべてTruthyであれば最後の変数を表示

      例１）
      const a = 0;
      const b = 1;
      const c = 3;
      console.log(a && b && c)
      // 結果的に0を表示
      
      例2）
      const a = 1;
      const b = 2;
      const c = 3;
      console.log(a && b && c)
      // 結果的に3を表示

## OR条件
- ||を用いる  
  各変数の評価を実施。truthyの値が来たらそれを表示。  
  falsyの値の場合は次の変数を評価する

# 応用編

function hello(name) {
  name = name || 'Tom';
  console.log('Hello ' + name);
}

hello()

let name;

name && hello(name);
