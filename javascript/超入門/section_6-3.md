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
- 「$()」で取得した要素に含まれる子孫要素のうち、()内のセレクタにマッチする要素を取得する。
  
      $('セレクタ1').find('セレクタ2')

## textメソッド
- 「$()」で取得した要素のコンテンツテクストを変更する  
  ※textContentプロパティと同じ役割を持つ(textContentは**p54参照**)

# その他一覧
## よく使うjqueryメソッドの一覧
**p284参照**

### コア機能
    $('セレクタ')
    $(配列またはオブジェクト)
    $ajax()

### トラバーサル
    next()
    find('セレクタ')
    find('セレクタ')
    children('セレクタ')
    each(function(){～})
    parent('セレクタ')
    siblings()
    prev()
### マニピュレーション(HTMLやCSSを操作する機能)
    addClass('クラス')
    removeClass('クラス')
    toggleClass('クラス')
    text(テキスト)
    hasClass('クラス')
    prepend(要素)
    attr('要素','値')
    attr('要素名')
    remove()

### イベント
    on('イベント', function(){～})
    event.preventDefault()

### わからない箇所のまとめ
float: left;  
cursor: pointer;
