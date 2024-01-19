## reduceメソッド

    const arry = [1, 2, 3, 4, 5];
    
    //reduceはすべての値を結合して一つの値にまとめる
    // 1 2
    // 3 3
    // 6 4
    // 10 5
    // 15(14行目)
    const result = arry.reduce(function(accu, curr) {
      console.log(accu, curr);
      return accu + curr;
    });
    
    console.log(result);
    
    //第二引数ありは初期値を明記してる(全ての配列がcurrに渡るようになる)
    // 0 1
    // 1 2
    // 3 3
    // 6 4
    // 10 5
    const result2 = arry.reduce(function(accu, curr) {
      console.log(accu, curr);
      return accu + curr;
    }, 1);
