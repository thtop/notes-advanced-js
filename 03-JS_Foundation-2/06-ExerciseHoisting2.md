# Exercise: Hoisting 2

```js
var favouriteFood = 'grapes';

var foodThoughts = function() {
  console.log('Original: ' + favouriteFood); // undefined

  var favouriteFood = 'sushi';

  console.log('New: ' + favouriteFood); // sushi
};

foodThoughts();
```

## const & let

```js
const favouriteFood = 'grapes';

const foodThoughts = function() {
  console.log('Original: ' + favouriteFood); // favouriteFood is not defined

  let favouriteFood = 'sushi';

  console.log('New: ' + favouriteFood);
};

foodThoughts();
```
