#宣告
- 宣告變數
  ```javascript
  //不使用var宣告的變數為全域變數
  var   (作用區域變數)
  let   (區域變數)
  const (區域不可變數)
  ```
- 範例
  - 不加var
  ```javascript
  function getNumber(){
    number = 19;
    console.log(number);  //19
  }
  console.log(number);  //19
  ```

  - var
  ```javascript
  function getNumber(){
    console.log(number);  //undefined
    var number = 19;
    console.log(number);  //19
  }
  ```
    
  - let
  ```javascript
  'use strict'  //嚴謹模式
  var a = 5;

  if (a === 5) {
    let a = 4; // The scope is inside the if-block

    console.log(a);  // 4
  } 

  console.log(a); // 5
  ```
    
  - const
  ```javascript
  //在嚴謹模式下會顯示TypeError: Assignment to constant variable.錯誤
  const a = 1;
  a = 2;
  console.log(a);  //1
  ```