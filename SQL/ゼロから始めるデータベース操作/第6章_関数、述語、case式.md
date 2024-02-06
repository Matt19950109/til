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

## 日付関数
## 変換関数
## 集約関数
