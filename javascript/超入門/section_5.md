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
