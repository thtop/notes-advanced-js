# Pure Functions

- Procedural => ... => FP
- return the same output givent the same input
- cannot modify anything outside of itself.
- No side effects.

```js
// no site effects
// input --> output

// share state
const array = [1, 2, 3];

// site effects
function mutateArray(arr) {
  arr.pop();
}

function mutateArray2(arr) {
  arr.forEach(item => {
    arr.push(1);
  });
}

console.log(mutateArray(array)); // undefined
console.log(mutateArray2(array)); // undefined
console.log(array); // [ 1, 2, 1, 1 ]
```
