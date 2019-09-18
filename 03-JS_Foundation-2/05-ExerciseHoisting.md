# Exercise: Hoisting

## variables

```js
var one = 1;
var one = 2;

console.log(one); // 2
```

## function

```js
a(); // bye

function a() {
  console.log('hi');
}

function a() {
  console.log('bye');
}
```
