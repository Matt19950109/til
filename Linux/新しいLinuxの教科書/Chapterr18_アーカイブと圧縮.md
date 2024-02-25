# アーカイブと圧縮ファイル
- アーカイブ → 複数のファイルやディレクトリをまとめたファイル
- 慣習として「.tar」の拡張子を付与
※アーカイブ(tarコマンド) → 圧縮(gzipコマンド)する順番

# tarコマンド

### ブレース展開
bashで利用できる連番のリストを生成可能

    {<開始位置>..<終了位置>}

## アーカイブファイルの作成
    tar cf <アーカイブファイル> <アーカイブファイル元のファイルパス>
    
    例）
    tar cf dir1.tar dir1
    tar -cf dir1.tar dir1

## アーカイブファイルの内容確認
    tオプションを利用する
    tar tf dir1.tar

## アーカイブファイルの展開

    tar xf <アーカイブファイル>
    ※既に同名のファイルが存在してる場合は上書きされてしまう

## ファイルリストを表示するvオプション

    vオプションでファイルリスト表示
    tar cvf dir1.tar dir1
    
    tオプションにvオプションを加えて詳細情報の表示
    ※アーカイブの作成や展開時にはお勧めしない
    tar tvf dir1.tar

# gzipコマンド
- 慣習として「.gz」の拡張子を付与する

        gzip <圧縮元ファイル>

## 圧縮ファイルを展開
gzip -d ps.txt.gz または
gunzip ps.txt.gz

## 標準出力にgzipファイルを出力(-cオプション)
gzip -c ps.txt > pa_test.txt.gz

## tarとgzipを組み合わせる
- tarコマンドだけでtar+gzファイルを作成可能

    tarコマンドでtar+gz形式のファイルを作成
    tar czf dir1.tar.gz dir1
    
    tarコマンドでtar+gz形式のファイルを展開
    tar xzf dir1.tar.gz

### tarとgzipコマンドでtar+gzファイルを作成

※別で作成すると中間ファイル(dir1.tar)が作成されるが、  
パイプラインを使用した場合はその心配がない


# bzipコマンド
gzip同様ファイルの圧縮展開を行うコマンド
**gzipより圧縮率が高くデータ量が小さくなる反面、時間がかかる**
    
    bzip <圧縮元ファイル>
    ※.bz2という拡張子を付与される

## tarとbzip2を組み合わせる
    tar cjf dir1.tar.bz2 dir1

## その他の圧縮形式
### xzコマンド
- bzip形式よりもさらに優れているが時間はかかる

# zipコマンド
LINUX上ではあまり使用しないが、OSユーザとやり取りをするために使用

zip,unzipパッケージのインストール
    # yum install zip unzip

## zipファイルの作成
    zip -r <圧縮ファイル名> <圧縮太陽パス>
    zip -r 1.zip dir1
    
    圧縮したファイル内容の確認
    zipinfo dir1.zip
    
    zipファイルの展開
    unzip dir1.zip

    パスワード付きzipファイルの作成
    zip -er dir1.zip dir1
    対象ファイル名を表示せずにzipファイルを作成(qオプション)
    zip -rq dir1.zip dir1
    
    対象ファイル名を表示せずにzipファイルを展開
    unzip -q dir1.zip
