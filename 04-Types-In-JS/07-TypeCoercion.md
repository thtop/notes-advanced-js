# Type Coercion

- the language converting a certain type to another type

```js
console.log(1 == '1'); // true

console.log(1 === '1'); // true

console.log(-0 === +0); // true

console.log(Object.is(-0, +0)); // false

console.log(NaN === NaN); // false
```

- [compare table](https://dorey.github.io/JavaScript-Equality-Table/)
- [Equality comparisons and sameness
  ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
- [ECMA Comparison Algorithm](https://www.ecma-international.org/ecma-262/5.1/#sec-11.9.3)
