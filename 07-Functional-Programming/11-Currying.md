# Currying

- save memory

```js
const multiply = (a, b) => a * b;

// Currying
const curriedMultiply = a => b => a * b;
console.log(curriedMultiply(5)(3)); //

const curriedMultiplyBy5 = curriedMultiply(5);
const curriedMultiplyBy10 = curriedMultiply(10);

console.log(curriedMultiplyBy5(5)); // 25
console.log(curriedMultiplyBy10(5)); // 50
```
