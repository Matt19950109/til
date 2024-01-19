
    const arry = [1, 2, 3, 4, 5];
    
    arry.forEach(function(v, i, arry) {
      console.log(v)
    });
    
    //新しい配列を作成するmap
    //以下の記述だと配列を反復した配列が作成される
    const newArry = arry.map(function(v, i, arry) {
      console.log(v);
      return arry ;
    });
    
    console.log(arry, newArry);
    
    //truthyとfalsyを区別して値を抽出する
    const filterArry = arry.filter(function(v, i, arry) {
      console.log(v);
      return i === 1;
    });
    
    console.log(filterArry);
