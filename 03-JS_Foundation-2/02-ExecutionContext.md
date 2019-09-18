# Execution Context

```js
function printName() {
  return 'Thamonwan Maneechan';
}

function findName() {
  return printName();
}

function sayMyName() {
  return findName();
}

console.log(sayMyName());
```

# Global Execution Context

- Global Object
- this

# Test (Browser)

- this
- window
- this === window // true

# Creation phase

- add variables & function to global object

# Execution phase

- run code
