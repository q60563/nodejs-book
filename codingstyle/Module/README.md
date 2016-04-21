#模組
- ES5

```javascript
//module.js
module.exports = {
  echo : function(){
    console.log('test');
  },
}

//app.js
var module = require('./module');
module.echo();

```

- ES6