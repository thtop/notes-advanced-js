# Exercise: Block Scope

```js
function loop() {
  for (var i = 0; i < 5; i++) {
    console.log(i);
  }
  console.log('final ' + i); // 5
}

loop();
```

# let

```js
function loop() {
  for (let i = 0; i < 5; i++) {
    console.log(i);
  }
  console.log('final ' + i); // ReferenceError: i is not defined
}

loop();
```
