# this

> this is the object that the function is a property of

```js
//obj.someFunct(this);

// console
// this === window

function a() {
  console.log(this);
}

a(); // window.a()
```

```js
function b() {
  'use strict';
  console.log(this);
}

b(); // undefined
```

```js
const obj = {
  name: 'Billy',
  sing: function() {
    return 'lalala ' + this.name;
  }
};

console.log(obj.sing()); // lalala Billy
```

new syntax

```js
const obj = {
  name: 'Billy',
  sing() {
    return 'lalala ' + this.name;
  },
  singAgain() {
    return 'lalala ' + this.name + '!'; // lalala Billy!
  }
};

console.log(obj.singAgain());
```

DRY

1. gives method access to their object

```js
const obj = {
  name: 'Billy',
  sing() {
    return 'lalala ' + this.name;
  },
  singAgain() {
    return this.sing() + '!'; // lalala Billy!
  }
};

console.log(obj.singAgain());
```

2. exedute same code for multiple objects

```js
function importPerson() {
  console.log(this.name + '!');
}

//window.importPerson();
const name = 'Sunny';

const obj1 = {
  name: 'Cassy',
  importPerson: importPerson
};

const obj2 = {
  name: 'Jacob',
  importPerson: importPerson
};

console.log(name); //Sunny
obj1.importPerson(); // Cassy!
obj2.importPerson(); //Jacob!
```

## Benefits of this

1. gives method access to their object
2. exedute same code for multiple objects
