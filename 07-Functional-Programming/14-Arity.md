# Arity

- the number of arguments a function takes.
- a function should have one or two parameter
  - function
  - curring
  - composition

```js
const compose = (f, g) => data => f(g(data)); // arity: 2
const makePositive = num => Math.abs(num); // arity: 1
```
