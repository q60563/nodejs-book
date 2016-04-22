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
var person = new Object();

var profile = new Object();
profile.name = 'Alex';
profile.age = 22;
profile.email = 'a0987@gmail.com';
profile['last name'] = 'Lin';

// 正確
var person = {};

var profile = {
  name: 'Alex',
  age: 22,
  email: 'a0987@gmail.com',
  'list name': 'Lin' 
};
```
