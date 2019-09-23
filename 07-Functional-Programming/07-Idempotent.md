# Idempotent / Idempotence

- same input -> different output

- The idea of impotence is a function that always returns or does what we expected to do.

- Another interesting feature of independents is this idea of being able to call yourself over and over and over or inside of yourself and you still get the same result.

```js
function notGood(num) {
  return Math.random(num);
}

console.log(notGood(5)); // same input -> different output

// ---

function notGood2(num) {
  console.log(num);
}

notGood2(5);

// call itself
console.log(Math.abs(-50)); // 50
console.log(Math.abs(Math.abs(-50))); // 50
```
