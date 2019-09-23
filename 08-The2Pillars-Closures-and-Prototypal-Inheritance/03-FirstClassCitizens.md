# First Class Citizens

- Functions are first class citizens in JS

```js
// 1. assign function to variable
var stuff = function() {};

// 2. pass function in to argument
function a(fn) {
  fn();
}

a(function() {
  console.log('hi there');
});

// 3. return function as a value from another function
function b() {
  return function c() {
    console.log('bye');
  };
}

b()(); // bye
const d = b();
d(); // bye
```
