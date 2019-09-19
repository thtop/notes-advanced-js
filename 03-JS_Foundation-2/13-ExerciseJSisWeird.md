# Exercise: JS is Weird

```js
function weird() {
  height = 50; // not see var === global env
  return height;
}

console.log(weird()); // 50
```

# use strict

```js
'use strict';
function weird() {
  height = 50;
  return height;
}

console.log(weird()); // ReferenceError: height is not defined
```

# not defined

```js
var heyhey = function doodle() {
  // do something
  //console.log(doodle()); // Maximum call stack size exceeded

  return 'heyhey';
};

console.log(heyhey()); // heyhey
//console.log(doodle); // doodle is not defined
//console.log(doodle()); // doodle is not defined
```
