## 即時関数(IIFE)

const moduleA = (function () {

console.log('IIFE called');

let privateVal = 1;
let publicVal = 10;

function publicFn() {
console.log('publicFn called: ' + publicVal);
}

function privateFn() {

}

return {
publicFn,
publicVal
}
})();

// 10、11が表示
console.log(moduleA.publocVal++)

// publicFn called: 10が表示される
(プリミティブ型はデータのコピーが渡されるため)
moduleA.publocFn()
