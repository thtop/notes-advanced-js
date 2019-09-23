# Higher Order Functions and Closures

## HOF

- Take one or more functions as arguments
- Or returns a function as a result (callback)

```js
// return function
const hof = () => () => 5;
console.log(hof()); // Function
console.log(hof()()); // 5

// receives as a parameter a function
const hof = fn => fn(5);
const result = hof(function a(x) {
  return x;
});

console.log(result); // 5
```

## Closure

- change state!

```js
const closure = function() {
  let count = 0; // change state!
  return function increment() {
    count++;
    return count;
  };
};

const incrementFn = closure();
console.log(incrementFn()); // 1
console.log(incrementFn()); // 2
console.log(incrementFn()); // 3
```

---

- Not to modify the sate

```js
const closure = function() {
  let count = 55;
  return function getCounter() {
    return count;
  };
};

const getCounterFn = closure();
console.log(getCounterFn()); // 1
console.log(getCounterFn()); // 2
console.log(getCounterFn()); // 3
```
