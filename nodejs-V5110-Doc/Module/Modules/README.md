# Modules
Node.js 有一個簡單的模組加載系統 。 在 Node.js 裡, 文件和模組是一對一的對應關係 。以下例子為 foo.js 加載同一目錄下的模組 circle.js 。

foo.js 內容:

```javascript
const circle = require('./circle.js');
console.log( `The area of a circle of radius 4 is ${circle.area(4)}`);
```

circle.js 內容:

```javascript
const PI = Math.PI;

exports.area = (r) => PI * r * r;  //計算圓面積

exports.circumference = (r) => 2 * PI * r;  //計算圓周長
```

透過 exports 物件使 circle.js 內 area() 和 circumference() 的函式可被導入 。


區域變數的模組為私有的，就像模組被包附在函式一樣 。在本例中變數 PI 是專屬於 circle.js 。

如果你想要將導入的模組像函式一樣(如建構函式)或者先導入模組後在賦值，使用 module.exports 而不是 exports.

如下 bar.js 導入一個 square 模組, 導出一個建構函式:

```javascript
const square = require('./square.js');
var mySquare = square(2);
console.log(`The area of my square is ${mySquare.area()}`);
```

定義 square 模組在 square.js :

```javascript
// assigning to exports will not modify module, must use module.exports
module.exports = (width) => {
  return {
    area: () => width * width
  };
}
```

模組系統由 require("module") 模組實現 。