## モジュール
- html上で以下の記述が必要  
        <script type="module" src="moduleB.js"></script>

## import
- モジュールの読み込みに使用

## export
- モジュールの露出に使用

## コード例
- moduleA.js

        //別ファイルにて
        //import {publicVal as val, publicFn as fn} from './moduleA.js';で流用が可能
        export let publicVal = 0;
        
        export function publicFn() {
          console.log('publicFn called:');
        }
        
        //変数に格納していない
        //別ファイルにて'import defaultValを記載することで流用が可能'
        export default 0;
