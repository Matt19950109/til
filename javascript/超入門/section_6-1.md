# SECTION 6 jQuery入門
## jqueryとは
- プログラミングで良く行われる定型的な処理を書きやすくしてくれるライブラリ  
  ※jqueryについて調べるときはバージョンが1.9以上であることを確認する

１．イベントを設定したい要素を取得する  
２．その要素にイベントを設定する  
３．イベントが発生したときの処理を実行する  

## HTMLが読み込まれたらfunction以降の処理を実行
    $(document).ready(function(){
      //処理を記載
    });

# jqueryを使用してサブメニューを開閉する
    $(document).ready(function(){
      $('.submenu h3').on('click',function(){
        $(this).next().toggleClass('hidden');
      })
    });
## jqueryで要素を取得する$()メソッド
    $('セレクタ')  
    $('.submit h3')
    ※querySelectorAllメソッドと同じような働きをする

- querySelectorAllメソッド→要素を配列のような形で取得する
- $()メソッド→jqueryオブジェクトに変換されるため、メソッドとプロパティを所持している
  
## onメソッド
- イベントを設定するjqueryのメソッド
  
      $('')で取得した要素.on('①イベント名',function(){
          //②イベントが発生したときの処理
      })
      ※①はイベント名(click,submit)などを指定
       ②のパラメータをfunctionにして処理内容を記載する

- $()で取得した要素が複数ある場合、すべてにメソッドを実行する

## next()メソッド
- トラバーサルと呼ばれるjqueryメソッドの一つ。  
  ※トラバーサル…$()で取得した要素から「すぐ次」「子要素」「親要素」など**相対的な位置関係で別の要素を取得すること**
## toggleClassメソッド
- 取得した要素に()内のパラメータで指定されているクラス名が  
  ついていなければ追加、ついていれば削除を実施するメソッド

      $(this).next().toggleClass('hidden');
