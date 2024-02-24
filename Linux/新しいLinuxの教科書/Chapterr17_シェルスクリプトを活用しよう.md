# シェルスクリプトの活用

## シェルスクリプトの欠点
- 大規模システムのプログラミングに不向き
- 高速性が必要な処理

## 演習1(日記を書くためのシェルスクリプト)

    #!/bin/bash
    
    # 日記データの保存ディレクトリ
    directory="${HOME}/diary"
    
    # データ保存ディレクトリがなければ作成する
    if [ ! -d "$directory" ]; then
      mkdir "$directory"
    fi
    
    # 日記ファイルパスの組み立て
    diaryfile="${directory}/$(date '+%Y-%m-%d').txt"
    
    # 日記ファイルがなければ(今日初めて書くならば)先頭に日付を挿入
    # fileに関する評価演算子(p293)
    if [ ! -e "$diaryfile" ]; then
      date '+%Y-%m-%d' > "$diaryfile"
    fi
    
    vim "$diaryfile"

### ローカル変数の宣言
local filepath=$1
