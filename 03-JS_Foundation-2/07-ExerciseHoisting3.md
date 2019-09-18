# Exercise: Hoisting 3

```js
function bigBrother() {
  function littleBrother() {
    return 'it is me!';
  }
  return littleBrother();
  function littleBrother() {
    return 'no me!';
  }
}

// Before running this code, what do you think the output is?
console.log(bigBrother()); // no me!
```

```js
function bigBrother() {
  // ** rewrite
  // littleBrother -> it is me!
  // littleBrother -> no me!

  function littleBrother() {
    return 'it is me!';
  }

  return littleBrother();

  function littleBrother() {
    return 'no me!';
  }
}

bigBrother();
```
