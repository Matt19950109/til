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

## 演習2(指定したパス配下のファイル一覧表示)
### ローカル変数の宣言
local filepath=$1

### 再帰呼び出し
- シェル関数の中から自分自身を呼び出して入れ子のように処理を行う方法

### 絶対パス表記からファイル名を取り出す

    最長マッチで前方一致した部分を取り除く
    ${変数名##パターン}

### インデント

### IFS-内部フィールド区切り文字
- bashはスペースで単語を区切るようになっているためIFSのデフォルト値(スペース sp、タブ ht、改行nl)からスペースを外す

        IFSを改行のみに設定
        IFS='
        '
 
 - IFSをバックアップしておき処理後に戻す

         _IFS=$IFS
         IFS=$"\n"
        ###必要な処理を行う
        IFS=$_IFS
 
## 最終的な例文
        #!/bin/bash
        
        list_recursive ()
        {
            local filepath=$1
            local indent=$2
        
            # インデント付きでパス部分を取り除いてファイル名を表示する
            echo "${indent}${filepath##*/}"
        
            if [ -d "$filepath" ]; then
            local fname

            IFS='
            '
            for fname in $(ls "$filepath")
            do
                # インデントにスペースを追加して再帰呼び出し
                list_recursive "${filepath}/${fname}""  $indent"
            done
            fi
        }
        
        list_recursive "$1" ""

## 演習3(検索コマンド)

### xargsコマンド
- 標準入力として「引数のリスト」を与える
- findコマンドと併用して使用される

### grepコマンド
- 対象ファイルが1つしかない時はマッチした行のみを表示  
  →-hオプションでファイル名を明記することが可能
- 対象が複数ファイルの時はファイル名も表示される

### xargsとgrepの併用

### ヒアドキュメント
- 複数行のテキストをシェルスクリプトにそのまま記述したいときに利用

        コマンド << 終了文字列
            ヒアドキュメントの内容
        終了文字列
        ※ヒアドキュメント内でのパラメータ展開を阻止するには「コマンド<<'終了文字列'」と記載

### エラーメッセージの表示
- 標準出力にはコマンド本来の結果を表示、標準エラー出力ではエラーメッセージを表示するという区別を意識する

## 完成したfindgrep.sh

            #!/bin/bash
            
            usage()
            {
            
                #
                local script_name=$(basename "$0")
            
                #
                cat << END
            Usage:$script_name PATTERN[PATH][NAME_PATTERN]
            find file in current directory recursively,and print lines which directory 
            NAME_PATTERN ～以下省略
            
            END
            }
            
            # 
            if [ "$#" -wq 0 ]; then
                usage
                exit 1
            fi
            
            pattern=$1
            directory=$2
            name=$3
            
            #
            #
            if [ -z "$directory"]; then
                directory="."
            fi
            
            #
            #
            if[ -z "$name" ]; then
                name='*'
            fi
            
            #
            if[ ! -d "$directory" ]; then
                echo "$0: ${directory}:No such directory" 1>&2
                exit 2
            fi
            
            find "$directory" -type f -name "$name" | xargs grep -nH "$pattern"
