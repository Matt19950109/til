## ファイルを探す

直下のファイルのみではなく、ディレクトリツリーを下って検索条件に一致するファイルをすべて表示する

    find <検索開始ディレクトリ> <検索条件> <アクション>
    $ find . -name file-1.txt -print

### 第一引数のオプション
- ファイル名で探す-name,-inameオプション  
※.や?で検索する場合、''か""を使用する

- ファイル種別を-typeで指定

        -type f → 通常ファイル
        -type d → ディレクトリ
        -type l → シンボリックリンク

### 複数の検索条件の指定
        $ find . -type f -a -name '*.txt' -print
        ※-aは省略可能

## locateコマンド
- パス名の一部を指定してファイルを探すためのコマンド
- このDBのみを検索するため高速に動作する

        locate [オプション] <検索パターン>
        -i → 大文字小文字を区別しない
        -b → ファイルのみを検索

## コマンドの使い方を調べる

### --helpオプション

### manコマンド(マニュアルを表示する)
- man <調べたいコマンド名>

        例）
        manについて調べる
        man man
        
        キーワードで調べる
        man -k <キーワード>
        
        セクションで調べる
        man <セクション番号> <名前>


## コマンドを探す
catコマンドなどはシェルがコマンドを実行する時に  
$PATHという環境変数に設定された場所から自動的にコマンドを探してくれる

### サーチパス
$PATHで設定する**コマンドを探すディレクトリ**

### whichコマンド
シェルが実際にどのファイルを実行するか確認する

            which cat
