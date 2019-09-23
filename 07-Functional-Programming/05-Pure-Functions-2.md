# Pure Functions 2

- Procedural => ... => FP
- return the same output givent the same input
- cannot modify anything outside of itself.
- No side effects.

```js
// no site effects
// input --> output

// shared state
const array = [1, 2, 3];

// No site effects
function removeLastItem(arr) {
  const newArray = [].concat(arr);
  newArray.pop();
  return newArray;
}

function multipylBy2(arr) {
  return arr.map(item => item * 2);
}

const array2 = removeLastItem(array);
const array3 = multipylBy2(array);
console.log(array); // [ 1, 2, 3 ]
console.log(array2); // [ 1, 2 ]
console.log(array3); // [ 2, 4, 6 ]
```

---

```js
// site effects
function a() {
  console.log('hi');
}

a();
```

---

## input -> output

```js
function a(num1, num2) {
  return num1 + num2;
}

//console.log(a(3, 4)); // 7

// Referential Transparency

function b(num) {
  return num * 2;
}

// b(7);
console.log(b(a(3, 4))); //
```

## Very easy to

- test
- Compose
- Avoids a lot of bugs
- Because we have no mutations
- No shared state.
- Predictable functions
