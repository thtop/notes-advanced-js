# Exercise: Type Coercion

```js
/**
false == '';
false == [];
false == {};
'' == 0;
'' == [];
'' == {};
0 == [];
0 == {};
0 == null;
*/

console.log(false == ''); // true
console.log(false == []); // true
console.log(false == {}); // false
console.log('' == 0); // true
console.log('' == []); // true
console.log('' == {}); // false
console.log(0 == []); // true
console.log(0 == {}); // false
console.log(0 == null); // false
```
