## Symbol
- プロパティの重複を避けるため必ず一意の値を返す関数
- コンストラクター関数とは異なり、new演算子を用いない

const s = Symbol('hello');
const s2 = Symbol('hello');
console.log(s === s2)　→ falseを返却する

### プロトタイプ汚染
- スクリプトにより独自でprototypeのメソッドを増やして拡張すること
