# Dateオブジェクトから残り時間を計算する

    function countdown(due) {
      const now = new Date();
    
      const rest = due.getTime() - now.getTime();
      const sec = Math.floor(rest / 1000) % 60;
      const min = Math.floor(rest / 1000 / 60) % 60;
      const hours = Math.floor(rest / 1000 / 60 / 60) % 24;
      const days = Math.floor(rest / 1000 / 60 / 60 / 24);
      const count = [days, hours, min, sec];
    
      return count;
    }
