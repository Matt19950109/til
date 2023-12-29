### NaN
Not a Numberの略。  
**数値として期待された値が数値として返せない場合に表示される**

# AND条件とOR条件

## AND条件
- &&を用いる
  各変数を評価していき、falsyの値が来たらそれを表示。  
  指定した変数がすべてTruthyであれば最後の変数を表示

const a = 0;
const b = 1;
const c = 3;
console.log(a && b && c)
// 結果的に
