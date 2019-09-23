# bind() and curring

## bind()

```js
function multiply(a, b) {
  return a * b;
}

let multiplyByTwo = multiply.bind(this, 2);
let multiplyByTen = multiply.bind(this, 10);

console.log(multiplyByTwo); // [Function: bound multiply]

console.log(multiplyByTwo(2)); // 4
console.log(multiplyByTen(2)); // 20
```

## Function Curring

```js
function multiply(a) {
  return function(b) {
    return a * b;
  };
}

let multiplyByTwo = multiply(2);
let multiplyByTen = multiply(10);

console.log(multiplyByTwo); // [Function: bound multiply]

console.log(multiplyByTwo(2)); // 4
console.log(multiplyByTen(2)); // 20
```
