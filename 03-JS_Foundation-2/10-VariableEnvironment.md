# Variable Envionment

- Execution Context (function)

  - this
  - arguments
  - Variable Environment

```js
function two() {
  // local environment
  var isValid; // undefined
}

function one() {
  var isValid = true; // local environment
  two();
}

var isValod = false; // global -> false
console.log(one()); // undefined
```
