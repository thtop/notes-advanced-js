# Exercise: this Keyword

```js
var b = {
  name: 'b jay',
  say() {
    console.log(this); // { name: 'b jay', say: [Function: say] }
  }
};

var c = {
  name: 'c jay',
  say() {
    return function() {
      console.log(this); // window

      // c.say()();
      // => c.say()
      // => ()
    };
  }
};

var d = {
  name: 'd jay',
  say() {
    return () => console.log(this); // { name: 'd jay', say: [Function: say] }
  }
};

d.say()();
```
