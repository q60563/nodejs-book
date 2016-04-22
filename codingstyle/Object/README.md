#物件
- Array

```javascript
// 錯誤
const items = new Array();

// 正確
const items = [];
```
- Object

```javascript
// 錯誤
var o = new Object();

var o2 = new Object();
o2.one = 0;
o2.two = 1;
o2.three = 2;
o2['strange key'] = 3;

// 正確
var o = {};

var o2 = {
  one: 0,
  two: 1,
  three: 2,
  'strange key': 3
};
```
