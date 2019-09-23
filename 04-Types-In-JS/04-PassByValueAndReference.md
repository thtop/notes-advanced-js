# Pass By Value vs Pass By Reference

- Primitive types => pass by value
- Reference types => pass by reference

```js
// primitive
var a = 5;
var b = a;

b++;
/**
a => 5
b => 6
*/

// reference
const obj1 = { name: 'Yao', password: '123' };
const obj2 = obj1;

obj2.password = 'easypeasy';

console.log(obj1);
console.log(obj2);

/**
{ name: 'Yao', password: 'easypeasy' }
{ name: 'Yao', password: 'easypeasy' }
/*

```

---

```js
var c = [1, 2, 3, 4, 5];
var d = c;

d.push(223423);

console.log(c);
console.log(d);

/**
[ 1, 2, 3, 4, 5, 223423 ]
[ 1, 2, 3, 4, 5, 223423 ]
*/
```

## concat (clone array)

```js
var c = [1, 2, 3, 4, 5];
var d = [].concat(c);

d.push(223423);

console.log(c);
console.log(d);

/**
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4, 5, 223423 ]
*/
```

## assign (clone obj)

```js
let obj = { a: 'a', b: 'b', c: 'c' };
let clone = Object.assign({}, obj);

obj.c = 5;
console.log(obj);
console.log(clone);

/**
{ a: 'a', b: 'b', c: 5 }
{ a: 'a', b: 'b', c: 'c' }
*/
```

## Spread operator

```js
let obj = { a: 'a', b: 'b', c: 'c' };
let clone = { ...obj };

obj.c = 5;
console.log(obj);
console.log(clone);

/**
{ a: 'a', b: 'b', c: 5 }
{ a: 'a', b: 'b', c: 'c' }
*/
```

## obj inside obj

```js
let obj = {
  a: 'a',
  b: 'b',
  c: {
    deep: 'try and copy me'
  }
};

let clone1 = Object.assign({}, obj);
let clone2 = { ...obj };

obj.c.deep = 'hahaha';
console.log('obj: ', obj);
console.log('clone1: ', clone1);
console.log('clone2: ', clone2);

/**

obj:  { a: 'a', b: 'b', c: { deep: 'hahaha' } }
clone1:  { a: 'a', b: 'b', c: { deep: 'hahaha' } }
clone2:  { a: 'a', b: 'b', c: { deep: 'hahaha' } }

*/
```

## JSON.parse

```js
let obj = {
  a: 'a',
  b: 'b',
  c: {
    deep: 'try and copy me'
  }
};

let clone1 = Object.assign({}, obj);
let clone2 = { ...obj };

let superClone = JSON.parse(JSON.stringify(obj));

obj.c.deep = 'hahaha';
console.log('obj: ', obj);
console.log('clone1: ', clone1);
console.log('clone2: ', clone2);
console.log('superClone: ', superClone);

/**

obj:  { a: 'a', b: 'b', c: { deep: 'hahaha' } }
clone1:  { a: 'a', b: 'b', c: { deep: 'hahaha' } }
clone2:  { a: 'a', b: 'b', c: { deep: 'hahaha' } }
superClone:  { a: 'a', b: 'b', c: { deep: 'try and copy me' } }


*/
```
