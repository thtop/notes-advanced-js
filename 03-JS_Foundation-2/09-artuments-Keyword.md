# arguments Keyword

```js
function marry(person1, person2) {
  console.log(arguments); // { '0': 'Tim', '1': 'Tina' }
  console.log(Array.from(arguments)); // [ 'Tim', 'Tina' ]

  return `${person1} is now married to ${person2}`;
}

console.log(marry('Tim', 'Tina'));
```

## Rest Paramaters

```js
function marry(...args) {
  return `${args[0]} is now married to ${args[1]}`;
}

console.log(marry('Tim', 'Tina'));
```

## {} Empry arguments object

```js
// Function Expression
var canada = () => {
  console.log('cold');
};

// Function Declaration
function india() {
  console.log(arguments); // [Arguments] {}
  console.log('warm');
}

india();
```
