# 正規表現の代表的なパターン


- [～]　→　中で囲まれた文字のいずれか一つにマッチ<br>
　(例) [a-z]：何かしらの英字が来たらマッチ

- /d　→　数字にマッチ

- {n , m}　→　直前の文字がn文字以上、m文字以内の回数が続くものにマッチ

- { n }　→　直前の文字がn回続くものにマッチ

- .(ピリオド)　→　改行以外のどの1文字にもマッチ

- +　→　直前の文字が1回以上繰り返される場合にマッチ

- /A　→　直後の文字が先頭にある文字列にマッチ

- /z　→　直前の文字が末尾にある文字列にマッチ

- [ぁ-んァ-ヶ一-龥々]　→　角括弧に囲まれたかな、カナ、漢字のいずれかにマッチ

- ?=　→　直後に設定した文字が続く文字列にマッチ

- *?　→　直前に設定した文字が0回以上続く文字列にマッチ
