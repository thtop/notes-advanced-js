# Scope Chain

```js
var x = 'x';

function findName() {
  console.log(x); // x
  var b = 'b';
  return printName();
}

function printName() {
  console.log(x); // x
  var c = 'c';
  return 'Andrei Neagoie';
}

function sayMyName() {
  var a = 'a';
  return findName();
}

console.log(sayMyName());
```

# Function Lexical Environment

```js
function sayMyName() {
  var a = 'a';
  return function findName() {
    var b = 'b';
    //console.log(c);
    return function printName() {
      var c = 'c';
      console.log(a); // a
      console.log(b); // b
      console.log(c); // c
      return 'Andrei Neagoie';
    };
  };
}

console.log(sayMyName()); // [Function: findName]
console.log(sayMyName()()); // [Function: printName]
console.log(sayMyName()()()); // Andrei Neagoie
```

# Error

```js
function sayMyName() {
  var a = 'a';
  return function findName() {
    var b = 'b';
    console.log(c); // ReferenceError: c is not defined
    return function printName() {
      var c = 'c';
      return 'Andrei Neagoie';
    };
  };
}

console.log(sayMyName()()());
```

# Global

```js
var c = 'Global c';

function sayMyName() {
  var a = 'a';
  return function findName() {
    var b = 'b';
    console.log(c);
    return function printName() {
      var c = 'c';
      return 'Andrei Neagoie';
    };
  };
}

console.log(sayMyName()()()); // Global c
```
