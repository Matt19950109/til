## リモートから情報を取得する(fetch)
    git fetch <リモート名>
    git fetch origin
    
    (fetchで取得した内容が更新されたファイルを確認する)
    git branch -a 
    
    ワークツリーにリモート内容を取り込む
    
    ※originリポジトリのマスターブランチの情報を取り込むコマンド
    git merge origin master
    
    
    pullの注意点
    ※今自分がいるブランチに無常件でプルした内容が反映される
    masterブランチにいて何も変更をしてない時にpullを使用するのは良い

## リモートの詳細情報を表示する
    git remote show origin
    → git remoteよりも詳しいリモート情報を取得できる

## リモートを変更する
    git remote rename <旧リモート名> <新リモート名>

