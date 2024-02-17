# ウィンドウ関数
- 別名OLAP関数(OnLine Analytical Processing)
- DBを使ってリアルタイムでデータ分析を行う処理のこと

        SELECT shohin_mei, shohin_bunrui, hanbai_tanka,
            RANK () OVER (PARTITION BY shohin_bunrui
                          ORDER BY hanbai_tanka) AS ranking
        
        ・PARTITION BY → 順位をつける対象」の範囲を指定
        ・ORDER BY → どの列をどんな順序で順位付けするかを指定

# ウィンドウ専用関数の種類
- RANK → ランキングを算出。後続順位が飛び出る
- DENSE_RANK → ランキング算出。後続順位が飛ばない
- ROW_NUMBER → 一意な連番を付与する(同順位のものはDBMSが適当な順序でランク付けする)
**ウィンドウ関数は引数を取らないため常に()の中は空っぽ**
