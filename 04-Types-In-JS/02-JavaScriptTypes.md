# JavaScript Types

1. number
2. boolean
3. string
4. undefined
5. null
6. Symblo
7. object

---

## Primitive types

- data that only represents a single value

1. number
2. boolean
3. string
4. undefined
5. null
6. Symblo

---

## None Promitive Type

- doesn't contail the actual value directly.

- object
- array
- function

```js
// reference
function obj1 = {
    a: 'Tom'
}

```

```js
console.log(typeof 5); // number

console.log(typeof true); // boolean

console.log(typeof 'To be or not to be'); // string

console.log(typeof undefined); // undefined => absence of difination

console.log(typeof Symbol('just me')); // symbol

//**************
// object
console.log(typeof null); // object => absence of value

console.log(typeof {}); // object

console.log(typeof []); // object

console.log(typeof function() {}); // function => object

console.log(typeof Math); // object
console.log(typeof Infinity); // number
```

```js
function a() {
  return 5;
}

a.hi = 'hihihihi';

console.log(a.hi); // hihihihi
```

## built-on objects

- [Standard built-in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)

## Wrapper object

```js
true.toString(); // "true"

Boolean(true).toString();
```
