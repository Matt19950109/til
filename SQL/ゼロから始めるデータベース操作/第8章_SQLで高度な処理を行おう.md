# ウィンドウ関数
- 別名OLAP関数(OnLine Analytical Processing)
- DBを使ってリアルタイムでデータ分析を行う処理のこと

SELECT shohin_mei, shohin_bunrui, hanbai_tanka,
    RANK () OVER (PARTITION BY shohin_bunrui
                  ORDER BY hanbai_tanka) AS ranking
