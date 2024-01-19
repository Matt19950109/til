## WeakMap

- 弱い参照でオブジェクトを保持するコレクション
- キーとなるのは必ずオブジェクト

## コード例

    const wm = new WeakMap();
    
    //オブジェクト削除時にキーとバリューペアも削除される
    let o = {};
    
    //値を更新
    wm.set(o, 'value1');
    
    //一旦以下のように削除すると既存の宣言した
    //オブジェクトを呼び出すことはできない
    //(ガベージコレクション)
    o = null;
    
    //undefinedが表示される
    o = {};
    
    //値を取得
    console.log(wm.get(o));
    
    //存在の有無を確認
    console.log(wm.has(o));
    
    //削除
    console.log(wm.delete(o))
    
    //weakmapはfor ofといった反復処理はできない
