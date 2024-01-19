## 代表的な配列

    const arry = [1,2,3,4,5]
    
    //末尾に新たな配列を追加
    arry.push(6)
    
    //末尾の配列を削除して戻り値で返す
    const result = arry.pop();
    
    //6が表示される
    console.log(result);
    
    //配列の先頭の値を削除
    arry.shift()
    
    //配列の先頭に引数の値を追加され個数を表示
    arry.unshift(0);
    
    //引数の開始位置と個数を入力し削除を実施
    //第三引数以降は切り取った個所に代入する値
    arry.splice(0, 1)
    
    //複数の配列同士を結合
    const arry2 = ary.concat([6,7,8])
    const arry3 = ([0, ...arry, 6,7,8]);

