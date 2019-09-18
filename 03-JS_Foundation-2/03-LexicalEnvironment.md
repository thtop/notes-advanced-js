# Lexical Environment

- where you write something

- printName()
- findName()
  - a()
- sayMyName()
- global()

```js
function printName() {
  return 'Thamonwan Maneechan';
}

function findName() {
  function a() {}
  return printName();
}

function sayMyName() {
  return findName();
}

console.log(sayMyName());
```

> In javascript our **laxical scope** (available data + variables where the function was defined) determines our available variables. Not where the function is called (**dynamic scope**)
