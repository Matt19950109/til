# 5-01 Dateオブジェクトから残り時間を計算する

    function countdown(due) {
      const now = new Date();
    
      const rest = due.getTime() - now.getTime();
      const sec = Math.floor(rest / 1000) /* ミリ秒→秒 */ % 60;
      const min = Math.floor(rest / 1000 / 60) /* 秒→分 */% 60;
      const hours = Math.floor(rest / 1000 / 60 / 60) /* 分→時 */ % 24;
      const days = Math.floor(rest / 1000 / 60 / 60 / 24);/* 時→日 */
      const count = [days, hours, min, sec];
    
      return count;
    }

## setTimeoutメソッド

        指定した待ち時間後にファンクションを一度だけ実行するメソッド
        setTimeout(function, 待ち時間)
        ※引数1のfunctionには()をつけてはいけない

        →なぜかというとfunction、メソッド名後の()には「その場で実行する」という意味があるため

## Dateオブジェクトに日時を設定する別の方法

        const goal = new Date(2025, 4, 3);
        ※new Date()の()内にパラメータを含めることにより、あらかじめ日時を設定した状態で初期化が可能
        →「年」、「月」は必須

## padstartメソッド
- 桁数を揃えるためのメソッド

        ある文字列.padstart(揃える文字数, 埋め合わせ用の文字)
        例）
        String(counter[2]).padStart(2, '0');
        ※(counter[2])部分で数値を返す場合は「String()」をはさむことによりデータ型を変更している

# 5-02 プルダウンメニューで指定ページに遷移
- onchangeイベント…フォームに入力された内容が変わった時に発生するイベント  
  例）テキストフィールド→入力内容が変わる。プルダウンメニュー→選択項目が変わる

- locationオブジェクトのhrefプロパティ…表示しているページのURLを表す  
  ※locationオブジェクト…URLを調べたり、閲覧履歴を管理したりする機能がある

## ブール属性
- HTML属性のうち、「その属性があれば有効。なければ無効になるもの」

## CSSセレクタで要素を取得する
document.querySelector('CSSセレクタ')

### タイプレセクタと属性セレクタの違い
- タイプセレクタ…要素の種類に基づいてスタイルを指定する
  例）h1、p、ul、liなど
- 属性セレクタ…特定の条件を満たす要素を選択し、それにスタイルを適用するのに役立つ

## switch文

        switch(調べる対象)　{
        case ○○:
          処理①を記述
          break;
        case △△:
        　処理②を記述
          break;
        case □□:
        　処理③を記述
        default:
          上記のいずれもが当てはまらない時の記述
        }

# 5-03 クッキーを使用してプライバシーポリシー承認パネルを作る

### cookieとは
- ブラウザとwebサーバ間で送受信され、主にECサイトやSNSサイトなどで
  ユーザーのログイン情報を管理するのに使用されている

### onclickイベント
- 要素がクリックされたときに発生する

        const agree = Cookies.get('cookie-agree');
        if(agree === 'yes') {
          console.log('クッキーを確認しました');
        }  else {
          console.log('クッキーを確認できません');
          document.getElementById('agreebtn').onclick = function(){
            Cookies.set('cookie-agree', 'yes', {expires: 7});
            };
        }
        //クッキー削除(テスト用)
        document.getElementById('testbtn').onclick = function() {
          Cookies.remove('cookie-agree');
        };

        ※Cookies.set('クッキー名', '値', {expires: 有効期限});
        js-cookieライブラリが提供するメソッドで指定した条件でクッキーを保存する

### removeChildメソッド
- 取得した要素に含まれる子要素または親要素のうち「()内のパラメータで指定した要素」を削除する

        取得した要素.removeChild(削除する要素)
        例）document.body.removeChild(panel);

# 5-04 画像切り替え

## querySelectorAllメソッド
- 指定したclass属性の複数の要素を取得する
  
        document.querySelectorAll('CSSセレクタ')
        例）
        const thumbs = document.querySelectorAll('.thumb');

## forEachメソッド
        配列.forEach(function(item, index) {
          //処理内容を記載
        });

## this
- イベントが発生した要素を指す  
  **※イベントに設定するファンクションの中で使用可能**

          item.onclick = function() {
            console.log(this.dataset.image);
          }

## data-○○属性
- ○○の部分は自分で決めてもよい
        取得した要素.dataset.○○
