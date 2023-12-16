# Dateオブジェクトから残り時間を計算する

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
