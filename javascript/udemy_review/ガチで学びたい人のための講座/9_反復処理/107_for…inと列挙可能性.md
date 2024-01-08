## for…in
**列挙可能プロパティ**に対して順不同で反復処理を実行
- プロトタイプチェーン内も列挙対象となる

## Symbolとfor…in

- Symbolで定義したプロパティはfor…inの列挙対象にならない


## 参考コード
    const s = Symbol();
    const obj = {
    	prop1: 'value1',
    	prop2: 'value2',
    	prop3: 'value3',
    
    	//変数をプロパティとしてオブジェクトに追加したい場合は[]を記載
    	//for…inの列挙ではシンボルのenumerableはfalseになる
    	[s]: 'value'
    }
    
    //Object.prototypeプロパティにmethodを格納
    //(この場合for…inの列挙に表示される)
    Object.prototype.method = function() {}
    
    //列挙で非表示にするよう変更
    Object.defineProperty(Object.prototype, 'method', {
    	enumerable: false
    }); 
    
    //指定のディスクリプタを確認
    const d = Object.getOwnPropertyDescriptor(Object.prototype, 'method');
    console.log(d);
    //※基本ビルトインオブジェクトはfalseで設定されている
    
    for(let key in obj) {
    
    	//hasOwnPropertyメソッドにて呼び出い元オブジェクトのプロパティのみ取得
    	//参照を保持してるprototypeは排除される
    	if(obj.hasOwnProperty(key)) {
    		console.log(key, obj[key]);
    	}
    }
    
    
