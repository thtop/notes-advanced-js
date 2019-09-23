# Exercise: Compare Objects

How would you compare two objects if they are pointing to a different location in memory but still have the same properties?

```js
var user1 = { name: 'nerd', org: 'dev' };
var user2 = { name: 'nerd', org: 'dev' };
var eq = user1 == user2;
alert(eq); // gives false
```

This is actually an interesting one! There is a simple solution, but it comes with a bit of a catch! [link](https://stackoverflow.com/questions/1068834/object-comparison-in-javascript)

```js
var user1 = { name: 'nerd', org: 'dev' };
var user2 = { name: 'nerd', org: 'dev' };
var eq = user1 === user2;
console.log(eq); // false

const result = JSON.stringify(user1) === JSON.stringify(user2);
console.log(result); // true
```
