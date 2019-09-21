# Higher Order Function

- function(): what to do and what data to use
- function(a, b): what it does later on we tell you what data we need
- HOF: give it the data & tell the function waht to do

# DRY

```js
// 1. function
function letAdamLogin() {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return 'Access Granted to Adam';
}

console.log(letAdamLogin());

// Eva
function letEvaLogin() {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return 'Access Granted to EVa';
}

console.log(letEvaLogin());
```

# Version 2 - 1

```js
function letUserLogin(user) {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return 'Access Granted to ' + user;
}

console.log(letUserLogin('Adam'));
console.log(letUserLogin('Eva'));
```

# Version 2 - 2

```js
// - What data to use.
const giveAccessTo = name => 'Access Greanted to ' + name;

function letUserLogin(user) {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return giveAccessTo(user);
}

console.log(letUserLogin('Adam'));
console.log(letUserLogin('Eva'));
```

# Version 2 - 3 DRI

```js
// - What data to use.
const giveAccessTo = name => 'Access Greanted to ' + name;

function letUserLogin(user) {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return giveAccessTo(user);
}

function letUserLogin(admin) {
  let array = [];
  for (let i = 0; i < 5000000; i++) {
    array.push(i);
  }
  return giveAccessTo(admin);
}

console.log(letUserLogin('Adam'));
console.log(letUserLogin('Eva'));
```

# Version 3

```js
// tell it what data to user + function what to do
const giveAccessTo = name => 'Access Greanted to ' + name;

function authenticate(verify) {
  let array = [];
  for (let i = 0; i < verify; i++) {
    array.push(i);
  }
  return true;
}

function letPerson(person, fn) {
  if (person.level === 'admin') {
    fn(5000000);
  } else if (person.level === 'user') {
    fn(10000);
  }
  return giveAccessTo(person.name);
}

console.log(letPerson({ level: 'user', name: 'Tim' }, authenticate));
console.log(letPerson({ level: 'admin', name: 'Sally' }, authenticate));
```

# Version 3 - 1

```js
// tell it what data to user + function what to do
const giveAccessTo = name => 'Access Greanted to ' + name;

function authenticate(verify) {
  let array = [];
  for (let i = 0; i < verify; i++) {
    array.push(i);
  }
  return giveAccessTo(person.name);
}

function sing(person) {
  return 'la lal la my name is ' + person.name;
}

function letPerson(person, fn) {
  if (person.level === 'admin') {
    return fn(person);
  } else if (person.level === 'user') {
    return fn(person);
  }
}

console.log(letPerson({ level: 'user', name: 'Tim' }, sing));
console.log(letPerson({ level: 'admin', name: 'Sally' }, sing));
```
