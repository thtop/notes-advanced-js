# Ecercise: Higher Order Functions

```js
const multiplyBy = function(num1) {
  return function(num2) {
    return num1 * num2;
  };
};

const multiplyByTwo = multiplyBy(2);
const multiplyByFive = multiplyBy(5);

console.log(multiplyByTwo(4));
console.log(multiplyByTwo(10));
console.log(multiplyByFive(6));
```

```js
const multiplyBy = num1 => num2 => num1 * num2;

console.log(multiplyBy(2)(4));

// const multiplyByTwo = multiplyBy(2);
// const multiplyByFive = multiplyBy(5);

// console.log(multiplyByTwo(4));
// console.log(multiplyByTwo(10));
// console.log(multiplyByFive(6));
```
