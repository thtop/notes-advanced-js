# Function Invocation

- assign memory
- assing a value to a vatiable
- running a function for the program to do something with those variables
- without funcitons the program dosen't do anything

## Function Expression

```js
var canada = function() {
  console.log('cold');
};

var canada = () {
  console.log('cold');
};

```

## Function Declaration

```js
function india() {
  console.log('warm');
}
```

## Run a function

- Function Invocation
- Call
- Execution

```js
canada();
india();
```

## Execution Context (function)

- global

  - global
  - this
  - global === this // true

- on top of global
  - this
  - arguments

```js
function marry(person1, person2) {
  console.log(arguments); // [Arguments] { '0': 'Tim', '1': 'Tina' }

  return `${person1} is now married to ${person2}`;
}

console.log(marry('Tim', 'Tina')); // Tim is now married to Tina
```
