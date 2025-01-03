# 6-1 いろいろな関数
## 関数の種類(ある値を入力するとそれに対応した値を出力する機能)

## 算術関数
### ABS(数値)
    SELECT m,
      ABS(m) AS abs_col
    FROM SampleMath

### MOD(被除数,除数)
    SELECT n,p,
        MOD(n,p) AS mod_col
    FROM SampleMath;

### ROUND(対象数,丸目の桁数)
    SELECT m,n,
        ROUND(m,n) AS round_col
    FROM SampleMath;

## 文字列関数
- 置換、切り出し、短縮などの操作を行う

### 連結
    SELECT str1, str2, str3
      str1 || str2 || str3 AS con_col
    FROM SampleStr;

### 文字数
        SELECT str1,
            LENGTH(str1) AS len_str
        FROM SampleStr;

### 置換
- REPLACE(対象文字列, 置換前の文字列, 置換後の文字列)

        SELECT str1, str2, str3,
            REPLACE (str1, str2, str3) AS rep_str
        FROM SampleStr;

### 文字の切り出し
- SUBSTRING(対象文字列 FROM 切り出し開始位置 FOR 切り出す文字列)

        SELECT str1,
            SUBSTRING(str1 FROM 3 FOR 2) AS sub_str
        FROM SampleStr;


## 日付関数
### 現在の日付
    SELECT CURRENT_DATE;

### 現在の時刻
    SELECT CURRENT_TIME;
### 現在の日時を取得する
    SELECT CURRENT_TIMESTAMP;
### 日付要素の取り出し
    EXTRACT (日付要素 FROM 日付)
    例）
    SELECT CURRENT_TIMESTAMP,
        EXTRACT(YEAR FROM CURRENT_TIMESTAMP) AS YEAR;
## 変換関数
### 型変換
    CAST(変換前の値 AS 変換するデータ型)
    例）
    SELECT CAST('0001' AS INTEGER) AS int_col;

### NULLを値に変換
    COALESCE(データ1, データ2, データ3…)
    例）
        SELECT COALESCE(str2, 'NULLです')
            FROM SampleStr;

# 6-2 述語
## 代表的な述語
- LIKE
- BETWEEN
- IS NULL,IS NOT NULL
- IN
- EXISTS

        SELECT shohin_mei, shiire_tanka
            FROM Shohin
        WHERE shiire_tanka IN (320, 500, 5000)

## NOT INとサブクエリ
        SELECT shohin_mei, hanbai_tanka
            FROM Shohin
        WHERE shohin_id IN (SELECT shohin_id
                                    FROM TenpoShohin
                                    WHERE tenpo_id = '000C')

## EXISTS述語
**EXISTSの引数は常に相関サブクエリ**
**左側には引数を取らない**

        SELECT shohin_mei, hanbai_tanka
            FROM Shohin AS s
        WHERE EXISTS (SELECT *
                            FROM TenpoShohin AS TS
                        WHERE TS.tenpo_id = '000C'
                            AND TS.shohin_id = S.Shohin_id );

# 6-3 CASE式
- 単純CASE式
- 検索CASE式(単純CASE式を包含している)

case式ｄで商品分類にA～Cを割り当てる

            SELECT shohin_mei,
                CASE WHEN shohin_bunrui = '衣服'
                THEN 'A:' || shohin_bunrui
                CASE WHEN shohin_bunrui = 'キッチン用品'
                THEN 'B:' || shohin_bunrui
                CASE WHEN shohin_bunrui = '事務用品'
                THEN 'C:' || shohin_bunrui
                ELSE NULL
            END AS abc_shohin_bunrui
        FROM Shohin;
