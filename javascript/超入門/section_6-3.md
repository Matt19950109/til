# jqueryを使用した空席状況の確認
## JSONとは
- JavaScriptのオブジェクト記法から派生したデータ形式  
  ※値だけではなく、プロパティ名もダブルクォートで囲む必要がある

### Ajaxの基本形
- ajaxとはJavaScriptからWebサーバにリクエストし、返されてきたデータもJavaScriptが受け取る仕組み
  
      $.ajax({url: 'data.json', dataType: 'json'})
      .done(function(data){
        //データがダウンロードできた時の処理
          }
        });
      })
      .fail(function(){
        //データがダウンロードできなかった時の処理
      });
## findメソッドなど

## よく使うjqueryメソッドの一覧
### わからない箇所のまとめ
float: left;  
cursor: pointer;
