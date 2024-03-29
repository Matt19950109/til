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
**主にSELECT句の後でないと登録不可**

# 集約関数のウィンドウ関数

        時系列でその時点でのリアルタイムの「累計を表示する」
        SELECT shohin_id, shohin_mei, hanbai_tanka,
                SUM(hanbai_tanka) OVER (ORDER BY shohin_id) AS current_sum
        FROM Shohin;

# フレーム(集計範囲)を指定する
- PRECEDING → カレントレコードを含む前の行を指定
- FOLLOWING → カレントレコードを含む後の行を指定

## 2つのORDER BY
OVER句内に必須のORDER BYとランキングをソートするためのORDER BYで2つのORDER BYを1文に記載することもある


# GROUPING演算子
- 昔はUNUON ALLを使ってドッキングさせる手法があった
GROUPING 演算子にはROLLUP,CUBE,GROUPING SETSの三種類存在している

## ROLLUP 合計と小計を一度に求める
        SELECT shohin_bunrui, SUM(hanbai_tanka) AS sum_tanka
                FROM Shohin
        GROUP BY ROLLUP(shohin_bunrui);

**集約キーの組み合わせが異なる結果を一度に計算する**

        SELECT shohin_bunrui, SUM(shohin_tanka) AS sum_tanka
                FROM Shohin
        GROUP BY ROLLUP(shohin_bunrui);

         shohin_bunrui | sum_tanka
        ---------------+-----------
                       |     16780
         キッチン用品  |     11180
         衣服          |      5000
         事務用品      |       600
        (4 行)
        超集合行に小計を含む合計が表示される

## GROUPING関数にて偽物のNULLを見分ける

        SELECT GROUPING(shohin_bunrui) AS shohin_bunrui,
                GROUPING(torokubi) AS torokubi, SUM(hanbai_tanka) AS sum_tanka
           FRON Shohin
        GROUP BY ROLLUP(shohin_bunrui, torokubi);

         shohin_bunrui | torokubi | sum_tanka
        ---------------+----------+-----------
                     1 |        1 |     16780
                     0 |        0 |      4000
                     0 |        0 |      6800
                     0 |        0 |      1000
                     0 |        0 |       880
                     0 |        0 |       100
                     0 |        0 |       500
                     0 |        0 |      3500
                     0 |        1 |     11180
                     0 |        1 |      5000
                     0 |        1 |       600
        (11 行)

### GROUPING関数を使用して合計の文字列を指定する
**GROUPING関数の0と1の分岐を利用して合計の文字列を代入する**

        SELECT CASE WHEN GROUPING(shohin_bunrui) = 1
                        THEN '商品分類 合計'
                        ELSE shohin_bunrui END AS shohin_bunrui,
                CASE WHEN GROUPING(torokubi) = 1
                        THEN '登録日　合計'
                        ELSE CAST(torokubi AS VARCHAR(16)) END AS torokubi,
                SUM(hanbai_tanka) AS sum_tanka
        FROM Shohin
        GROUP BY ROLLUP(shohin_bunrui, torokubi);
        
        
         shohin_bunrui |   torokubi   | sum_tanka
        ---------------+--------------+-----------
         商品分類 合計 | 登録日　合計 |     16780
         衣服          |              |      4000
         キッチン用品  | 2009-01-15   |      6800
         衣服          | 2009-09-20   |      1000
         キッチン用品  | 2008-04-28   |       880
         事務用品      | 2009-11-11   |       100
         事務用品      | 2009-09-11   |       500
         キッチン用品  | 2009-09-20   |      3500
         キッチン用品  | 登録日　合計 |     11180
         衣服          | 登録日　合計 |      5000
         事務用品      | 登録日　合計 |       600
        (11 行)


### CUBE データで積み木を作る
CUBEはすべての可能な組み合わせを一つの結果にまとめてしまう機能
組み合わせ数は2ⁿで表す

        shop=#         SELECT CASE WHEN GROUPING(shohin_bunrui) = 1
        shop-#                         THEN '商品分類 合計'
        shop-#                         ELSE shohin_bunrui END AS shohin_bunrui,
        shop-#                 CASE WHEN GROUPING(torokubi) = 1
        shop-#                         THEN '登録日　合計'
        shop-#                         ELSE CAST(torokubi AS VARCHAR(16)) END AS torokubi,
        shop-#                 SUM(hanbai_tanka) AS sum_tanka
        shop-#         FROM Shohin
        shop-#         GROUP BY CUBE(shohin_bunrui, torokubi);


         shohin_bunrui |   torokubi   | sum_tanka
        ---------------+--------------+-----------
         商品分類 合計 | 登録日　合計 |     16780
         衣服          |              |      4000
         キッチン用品  | 2009-01-15   |      6800
         衣服          | 2009-09-20   |      1000
         キッチン用品  | 2008-04-28   |       880
         事務用品      | 2009-11-11   |       100
         事務用品      | 2009-09-11   |       500
         キッチン用品  | 2009-09-20   |      3500
         キッチン用品  | 登録日　合計 |     11180
         衣服          | 登録日　合計 |      5000
         事務用品      | 登録日　合計 |       600
         商品分類 合計 |              |      4000
         商品分類 合計 | 2009-11-11   |       100
         商品分類 合計 | 2009-09-20   |      4500
         商品分類 合計 | 2009-09-11   |       500
         商品分類 合計 | 2009-01-15   |      6800
         商品分類 合計 | 2008-04-28   |       880
        (17 行)

## GROUPING SETS ほしい積み木だけを取得する
- ROLLUPやCUBEで求めた結果の一部のレコードだけを求めればよい場合に使用

        SELECT CASE WHEN GROUPING(shohin_bunrui) = 1
                    THEN '商品分類　合計'
                    ELSE shohin_bunrui END AS shohin_bunrui,
                CASE WHEN GROUPING(torokubi) = 1
                     THEN '登録日　合計'
                     ELSE CAST(torokubi AS VARCHAR(16)) END AS torokubi,
                SUM(hanbai_tanka) AS sum_tanka
        FROM Shohin
        GROUP BY GROUPING SETS (shohin_bunrui, torokubi);


         shohin_bunrui  |   torokubi   | sum_tanka
        ----------------+--------------+-----------
         キッチン用品   | 登録日　合計 |     11180
         衣服           | 登録日　合計 |      5000
         事務用品       | 登録日　合計 |       600
         商品分類　合計 |              |      4000
         商品分類　合計 | 2009-11-11   |       100
         商品分類　合計 | 2009-09-20   |      4500
         商品分類　合計 | 2009-09-11   |       500
         商品分類　合計 | 2009-01-15   |      6800
         商品分類　合計 | 2008-04-28   |       880
