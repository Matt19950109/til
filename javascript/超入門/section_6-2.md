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
        $('#wrapper, #nav').toggleClass('show');
      });
    });
    ※26行目はカンマで区切って複数のセレクタを指定している
    　各要素に「'」を指定する必要はない


### 確認用

    <div id="wrapper">
        <header>
        <div class="container">
            <div class="title-block">
                <h1>ドロワーナビゲーション</h1>
                <h2>メニューが「開いた」ときの状態を作る</h2>            
            </div>
            <div class="hamburger" id="open_nav">
                <img src="hamburger.png" alt="">
            </div>
        </div><!-- /.container -->
        </header>
        <main>
        <div class="container">
        <section>
            <div class="key">
                <img src="key.jpg" alt="">
            </div>
            <div class="content">
                <h1>ひとり旅でリフレッシュ</h1>
                <p>今月の特集は「ひとり旅」。<br>
                週末に行ける小さな旅行から人生を見つめる長旅まで、<br>
                充実のおひとり様プラン、紹介します。</p>
            </div>
            <div class="archive">
                <h3>特集アーカイブ</h3>
                <div class="archive-box">
                    <figure>
                        <img src="thumb1.jpg" alt="">
                        <figcaption>レトロな街の、楽しみ方</figcaption>
                    </figure>
                    <figure>
                        <img src="thumb2.jpg" alt="">
                        <figcaption>建築物を巡る旅</figcaption>
                    </figure>
                </div>
            </div>
        </section>
        </div><!-- /.container -->
        </main>
    
        <footer>
        <div class="container">
        <p>JavaScript Samples</p>
        </div><!-- /.container -->
        </footer>
    </div>
    
    <nav id="nav">
        <div class="logo"><img src="logo.svg" alt=""></div>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">今月の特集</a></li>
            <li><a href="#">ホテル検索</a></li>
            <li><a href="#">カフェ検索</a></li>
            <li><a href="#">お問い合わせ</a></li>
        </ul>
    </nav>
    <script src="../../_common/scripts/jquery-3.4.1.min.js"></script>
    <script>
    'use strict'
    
    $(document).ready(function(){
      $('#open_nav').on('click', function(){
        $('#wrapper, #nav').toggleClass('show');
      });
    });
    </script>
