#命名
- 基本規則
 - 可用字元：底線，字母，數字 
 - 字首不可為數字
 - 不允許使用關鍵字，保留字
 - 命名要有意義(name優於n)
 
 
- 變數,常數,JSON

```javascript
/**
 * 變數與JSON
 * 型態+單字 需要可以表達出用途(並採用小駝峰命名)
 * 小駝峰式命名法:第一個單字以小寫字母開始,第二個單字的首字母大寫
 */
var intYear = 25;
var strName = 'Danny';
var arrPool = [ 20, 14, 23, 22 ];
var jsonUserdata = { name: 'Danny', year:25 };
/**
 * 常數(不會改變之數值)
 * 一律採用全大寫並將每個單字用底線做分隔
 */
RESPBERRY_PI = 2
```


- 方法

```javascript
//動詞+用途或是該功能名(並採用小駝峰命名)
getUser = function () {
  return user;
}
```
- 類別(Class)

```javascript
//類別部份採用大駝峰式命名
function Bmi(){  
}
```

- 檔案

```javascript
/**
 * 檔案檔名一律為全小寫
 * 並且如果有多個單字在一起則使用底線做區隔
 */
檔案：raspberry_pi2.js

var rpi2 = require('./raspberry_pi2');
```
