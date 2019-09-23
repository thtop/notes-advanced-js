# Array.isArray()

```js
var array1 = ['1', '2', '3'];

var array2 = {
  0: '1',
  1: '2',
  3: '3'
};

const array3 = Array.isArray(['1', '2', '3']);
console.log(array3); // true

const array4 = Array.isArray({});
console.log(array4); // false
```
