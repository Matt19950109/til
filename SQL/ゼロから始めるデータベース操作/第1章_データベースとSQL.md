# 1-3 SQLの概要

## DDL
- データを格納する入れ物であるデータベースやテーブルを作成・削除する  

        CREATE：作成
        DROP：削除
        ALTER：構成を変更

## DML
- テーブルの行を検索・変更する

        SELECT：行を検索
        INSERT：新規行を登録
        UPDATE：行を更新
        DELETE：行を削除

## DCL
- データベースに実施した変更を確定・取り消しを行う

COMMIT：DBに対して実施した変更を確定する
ROLLBACK：DBに対して実施した変更を取り消す
GRANT：ユーザに操作の権限を与える
REVOKE：ユーザから操作の権限を奪う
