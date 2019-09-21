# Closures

```js
function a() {
  let grandpa = 'grandpa';
  return function b() {
    let father = 'father';
    return function c() {
      let son = 'son';
      return `${grandpa} -> ${father} -> ${son}`;
    };
  };
}

/*
console.log(a()); // [Function: b]
console.log(a()()); // [Function: c]
console.log(a()()()); // grandpa -> father -> son
*/

const one = a();
```

```js
const boo = string => name => name2 =>
  console.log(`${string} ${name} ${name2}`);

console.log(boo('hi')); // [Function]
console.log(boo('hi')('tim')); // [Function]
boo('hi')('tim')('becca'); // hi tim becca
```

```js
const boo = string => name => name2 =>
  console.log(`${string} ${name} ${name2}`);

const booString = boo('hi');
// 5 years
const booStringName = booString('Lexa');
booStringName('Praew');
```
