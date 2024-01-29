## リモートリポジトリを新規追加する
    git remote add origin
      <リモートレポジトリのURL>
    originの部分は任意で設定可能
    (githubでは慣習的にoriginを使用している)

## リモートリポジトリにプッシュ
    登録したリモートリポジトリに設定するコマンド
    ※-uと記載することで、
    　次回以降のorigin masterのプッシュは「git push」のみで実行できる
    git push -u origin master
