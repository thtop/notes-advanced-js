# call(), apply(), bind()

- `call()` and `apply()` are useful for borrowing methods from an object
- `bind()` is useful for us to call function later on with a certain context or certain keyword

## call()

```js
function a() {
  console.log('hi');
}

a.call(); // hi
a(); // hi
```

## apply()

```js
function a() {
  console.log('hi');
}

a.applly(); // hi
```

## Game

```js
const wizard = {
  name: 'Merlin',
  health: 50,
  heal() {
    return (this.health = 100);
  }
};

const archer = {
  name: 'Robin Hood',
  health: 30
};

console.log('1', archer); // 1 { name: 'Robin Hood', health: 30 }
wizard.heal.call(archer);
console.log('2', archer); // 2 { name: 'Robin Hood', health: 100 }
```

---

## call()

```js
const wizard = {
  name: 'Merlin',
  health: 50,
  heal(num1, num2) {
    return (this.health += num1 + num2);
  }
};

const archer = {
  name: 'Robin Hood',
  health: 30
};

console.log('1', archer); // 1 { name: 'Robin Hood', health: 30 }
wizard.heal.call(archer, 50, 30); // 2 { name: 'Robin Hood', health: 110 }
console.log('2', archer);
```

---

## apply()

```js
const wizard = {
  name: 'Merlin',
  health: 50,
  heal(num1, num2) {
    return (this.health += num1 + num2);
  }
};

const archer = {
  name: 'Robin Hood',
  health: 30
};

console.log('1', archer); // 1 { name: 'Robin Hood', health: 30 }
wizard.heal.apply(archer, [100, 30]); // 2 { name: 'Robin Hood', health: 160 }
console.log('2', archer);
```

---

## bind()

```js
const wizard = {
  name: 'Merlin',
  health: 50,
  heal(num1, num2) {
    return (this.health += num1 + num2);
  }
};

const archer = {
  name: 'Robin Hood',
  health: 30
};

console.log('1', archer); // 1 { name: 'Robin Hood', health: 30 }

//wizard.heal.bind(archer, 50, 30); // 2 { name: 'Robin Hood', health: 30 }

const healArcher = wizard.heal.bind(archer, 100, 30);
healArcher(); // 2 { name: 'Robin Hood', health: 160 }

console.log('2', archer);
```
