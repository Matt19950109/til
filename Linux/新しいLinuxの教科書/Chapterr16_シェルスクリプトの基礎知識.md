# シェルスクリプトの基本
    ; → 複数のコマンド間を区切ることで1行にまとめて記載
    \ → 途中で改行
    > → セカンダリプロンプト
    # → コメント

## 変数
<変数名> = <値>
**変数の値を参照するには変数名の前に「$」をつける**

### 変数の書き方のルール
- 代入時に$をつけない
- =の前後はスペースを入れない
- 変数名に利用できる文字はアルファベットと_のみ  
  ※一般的には環境変数に大文字、通常のシェル変数には小文字を用いる
- 変数名の区切りを明示する → ${}

## クォーティング
スペースをhy組めてコマンドの引数として指定したいときに使用  
例）"my file"

        ''(シングルクォート) → ありのままの文字を反映
        ""(ダブルクォート) → コマンド置換が有効
        ※ダブルクォートでもエスケープすれば文字として出力可能
## コマンド置換
現在日付のファイルを作成する
#!/bin/bash

filename=$(date '+%Y-%m-%d')
touch "$filename"

※以下のようにバッククォートでもコマンド置換が可能
echo "Today is `$date '+%Y-%m-%d'`"

## 位置パラメータ
### コマンドライン引数関連のシェル変数
    $0 → 実行時のシェルスクリプト名
    $1,$2 → コマンドライン引数の値
    $# → 位置パラメータの個数
    $@ → 全位置パラメータ。""で囲むとそれぞれのパラメータがダブルクォートで囲まれる
    $* → 全位置パラメータ。""で囲むと一つの文字列としてダブルクォートで囲まれる

## if文
    if <コマンド1>; then
    elif <コマンド2>; then
    else
    fi

※[は組み込み関数のため[の後ろはスペースで区切る必要がある

### lsやgrepなどのコマンドは終了ステータスと呼ばれる整数値を返す($?)
**コマンドが正常終了した場合は0、エラー時には0以外を返す**

-qオプション → quietモードで終了ステータスだけを利用したい場合に使う

代表的な文字列の評価演算子
-n str1 → str1が空文字列ではない
-z str1 → str1が空文字列である

p293-294if文で使用する評価演算子の一覧

特に明示がない限り、シェルスクリプトの最後に実行したコマンドの終了ステータスが  
シェルスクリプト自体の終了ステータスになる

exit <終了ステータス>

## for文
    for 変数名 in リスト
    do
        <繰り返す処理>
    done

### 例文(0001txtから連番のファイルを作成する)
    #!/bin/bash
    
    for i in $(seq 1 5)
    do
        touch "000${i}.txt"
    done

### コマンドライン引数を順に表示する
    #!/bin/bash
    
    for parameter in "$@"
    
    do
        echo "$parameter"
    done

## case文(指定された文字列がパターンにマッチするかを判断しマッチしたパターンに対応した処理を行う)

    case <文字列> in
        <パターン1>)
        処理1
            ;;
        <パターン2>)
        処理2
        ;;
    esac

## 例文
    #!/bin/bash
    
    case "$1" in
        *.txt)
            less "$1"
            ;;
        *.sh)
            vim "$1"
            ;;
        *)
        echo "not supported file : $1"
        ;;
    esac

## while文(指定した条件が真である限り繰り返し処理を行う)

    while <コマンド>
    do
        繰り返し処理
    done

### 例文(10以下の奇数を表示)
    #!/bin/bash
    
    i=1
    while [ "$1" -le 10 ]
    do
        echo "$1"
        i=$((i + 2))
    done

### 算術式展開
sh → exprという外部コマンドを使用
'expr $1 + 2'

bash → $((i + 2))

## シェル関数
    #!/bin/bash
    
    print_parameters ()
    {
        echo "\$1 = $1"
        echo "\$2 = $2"
        echo "\$3 = $3"
        echo "\$4 = $4"
    
        echo
        echo "$# arguments"]
        echo "script name = $0"
    }

### シェル関数の終了ステータス
    return <終了ステータス>
