## Storage
- ブラウザの保存領域にデータを格納するためのオブジェクト

### localstorage

    const obj = { a: 0 };
    const json = JSON.stringify(obj);
    
    // 検証ツールタブのlocalstorageに格納される
    localStorage.setItem('key', json);
    localStorage.setItem('key2', '2');
    
    //getItemで値を取得(同期処理を実施)
    const result = localStorage.getItem('key');
    const obj2 = JSON.parse(result);
    console.log(obj2);
    console.log(result);
    
