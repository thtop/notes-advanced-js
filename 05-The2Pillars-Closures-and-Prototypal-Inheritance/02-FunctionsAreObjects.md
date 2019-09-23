# Function are Objects

```js
function one() {
  return 2;
}
console.log(one()); // 2

const obj = {
  two: function() {
    return 3;
  }
};
console.log(obj.two()); // 3

const obj2 = {
  two() {
    return 4;
  }
};
console.log(obj2.two()); // 4

// call()
function three() {
  return 3;
}

console.log(three.call()); // 3
```

```js
// function constructor
const four = new Function('return 4');
console.log(four()); // 4

const four2 = new Function('num', 'return num');
console.log(four2(4)); // 4
```

```js
function woohooo() {
  console.log('wooohooo');
}

woohooo.yell = 'ahhhhhh';

/**
const specialObj = {
    yell: 'ahhhhhh',
    name: 'woohooo',
    (): console.log('woohooo')
}
*/

const obj = {};
```

- somefunct()
  - Code()
  - Name (optional)
  - Properties
    - .call()
    - .apply()
    - .bind()
