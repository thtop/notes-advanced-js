# Immutability

```js
const obj = { name: 'Commander Lexa' };
function clone(obj) {
  return { ...obj }; // this is pure.
}

//obj.name = 'Nana'; // mutating data

function updateName(obj) {
  const obj2 = clone(obj);
  obj2.name = 'Nana';
  return obj2;
}

const updatedObj = updateName(obj);
console.log(obj, updatedObj); // { name: 'Anfrei' } { name: 'Nana' }
```

- Not changing
  - the data
  - the state
    - making copies of the state and returning a new state every time.
