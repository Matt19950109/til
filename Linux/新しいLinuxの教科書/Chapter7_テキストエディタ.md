# テキストエディタとバイナリファイル

## Vim -デフォルトのエディタ
Vim → エディタ名称
vim → コマンド

### 起動と終了
    起動 → vim
    終了 → :q
    保存 → :w
    :q! → 保存せずに強制終了
vim newfile.txt

### Vimの編集操作

    h → 左に移動
    j → 下に移動
    k → 上に移動
    l → 右に移動

### 文字の削除と追加
    x → カーソル位置の文字を削除
    i → カーソル位置の左に文字を追加する
    a → カーソル位置の右に文字を追加

### 単語単位のカーソル移動
    w → 前方に単語1つ分移動
    b → 後方に単語1つ分移動
    W → スペース区切りで前方に単語1つ分移動
    B → スペース区切りで後方に単語1つ分移動

### 行番号での移動
    gg → 1行目に移動
    G → 最後の行に移動
    <数字> G → <数字> 行目に移動

## カット、コピー、ペースト

### vimの特殊な総省
    カット → デリート(delete)
    コピー → ヤンク(yank)
    ペースト → プット(put)

### デリート
    d$ → 行末までをデリート
    d0 → 行頭までをデリート
    x、dl → 1文字をデリート
    dw → 単語1つをデリート
    dgg → 最初の行までをデリート
    dG → 最後の行までをデリート

**カットしたものをpコマンドで貼付(プット)可能**

### ヤンク
デリートで削除するのではなく、単にコピーしたい場合はyコマンドを使用する

指定した現在の行のヤンクとデリート
    yy → カーソル行をヤンク
    dd → カーソル行をデリート

## 下の行と連結する
Jコマンドを使用する

## アンドゥ(元に戻す)とリドゥ(やり直し)
    アンドゥ(直前の動作を取り消して前の状態に戻る) → uを押下
    リドゥ(アンドゥを取り消す) → Ctrl + r

## 検索と置換
    /<文字列> → 下方向に向かって<文字列>を検索する
    ?<文字列> → 上方向に向かって<文字列>を検索する
    n → 次の検索結果に移動する
    N → 前の検索結果に移動する

### 置換
    %s/ <置換元文字列> / <置換後文字列> /g

### ヘルプとドキュメント
    vimtutor
    vimに付属してあるチュートリアル
    
    ヘルプコマンド
    :help
