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
## 変換関数
## 集約関数
