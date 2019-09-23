# Compose and Pipe

## Compose

- data --> fn --> data --> fn --> ...
- the definition compose ability is a system design principle that deals with the relationship between components.

```js
// Compose
// -50 * 3 -

const compose = (f, g) => data => f(g(data));

const multiplyBy3 = num => num * 3;
const makePositive = num => Math.abs(num);

const multiplyBy3AndMakePositive = compose(
  multiplyBy3,
  makePositive
);

const result = multiplyBy3AndMakePositive(-50);
console.log(result); // 150
```

---

## Pipe

```js
// Pipe
// fn1(fn2(fn3(50)))
// compose(fn2, fn2, fn3)(50)
// pipe(fn3, fn2, fn3)(50)

//const compose = (f, g) => data => f(g(data));
const pipe = (f, g) => data => g(f(data));

const multiplyBy3 = num => num * 3;
const makePositive = num => Math.abs(num);

const multiplyBy3AndMakePositive = pipe(
  multiplyBy3,
  makePositive
);

const result = multiplyBy3AndMakePositive(-50);
console.log(result); // 150
```
