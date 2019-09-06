# Idempotent

```js
function notGood(num) {
  return Math.random(num);
}

console.log(notGood(5));

function notGood2(num) {
  console.log(num);
}

notGood2(5);

// call yourself
console.log(Math.abs(-50)); // 50
console.log(Math.abs(Math.abs(-50))); // 50
```
