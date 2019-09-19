# Function Scope vs Block Scope

```js
// block scope
if (5 > 4) {
  var secret = '1234';
}
console.log(secret); // 1234

console.log(secret);

// function scope
function a() {
  var test = 'test';
}

//console.log(test); // ReferenceError
```

# Function scope

- var

# Block scope

- let
- const
