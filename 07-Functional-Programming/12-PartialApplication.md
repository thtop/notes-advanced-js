# Partial Application

- Partial application is a way for us to well partially apply a function.
- It's a process of producing a function with a smaller number of parameters.

```js
const multiply = (a, b, c) => a * b * c;

// Currying
const curriedMultiply = a => b => c => a * b * c;
console.log(curriedMultiply(3)(4)(10)); //120 -> one at a time

// Partial Application
const partialMultiplyBy5 = multiply.bind(null, 5);
console.log(partialMultiplyBy5(4, 10)); // 200 -> call the rest
```
