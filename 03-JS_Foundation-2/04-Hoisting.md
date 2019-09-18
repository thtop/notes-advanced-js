# Hoisting

- Global Execution Context

- Creation phase

  - Global Object
  - this
  - Hoisting

- Execution phase
  - Run Your Code

# var & function decaration

- var
- function

```js
console.log('1--------');
console.log(teddy); // undefined
sing(); // ohhh la la la

var teddy = 'bear';

function sing() {
  console.log('ohhh la la la');
}
```

# ( )

```js
console.log('1--------');

sing(); // sing is not defined

var teddy = 'bear';

(function sing() {
  console.log('ohhh la la la');
});
```

# const & let

```js
console.log('1--------');
console.log(teddy); // teddy is not defined

const teddy = 'bear';
```

# Function expression

- run after defined

```js
console.log('1--------');

console.log(sing); // undefined

//sing(); // sing is not a function

var sing = function() {
  console.log('ohhh la la la');
};

sing(); // ohhh la la la
```
