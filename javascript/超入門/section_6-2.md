## ハンバーガーメニューボタン

### ナビゲーションバーを画面右横に移す

                #nav {
                position: fixed;
                right: -270px; ←幅(width)をマイナス値。左横に寄せたい場合はプラス値で設定
                top: 0;
                width: 270px;
                height: 100%;
                }

## transformプロパティ
- 要素を移動、拡大・縮小、回転をするときに使用

      transform: translate3d(x軸の移動量、y軸の移動量、z軸の移動量)
      /* ドロワーが開かれたときのスタイル */
      .show {
          transform: translate3d(-270px, 0, 0);
      }

### 開閉機能をプログラミング

    $(document).ready(function(){
      $('#open_nav').on('click', function(){
        $('#wrapper', '#nav').toggleClass('show');
      });
    });
