# Dynamic Scope vs Lexical Scope

```js
const a = function() {
  console.log('a: ', this);
  const b = function() {
    console.log('b: ', this);
    const c = {
      hi: function() {
        console.log('c: ', this);
      }
    };
    c.hi(); // { hi: [Function: hi] }
  };
  b(); // window
};
a(); // window

// window.a(b())
```

## this

- this keywords is actually dynamically scoped
- that is it doesn't matter where it's run it matters how

```js
const obj = {
  name: 'Billy',
  sing() {
    console.log('a', this); // { name: 'Billy', sing: [Function: sing] }
    var anotherFunc = function() {
      console.log('b', this); // window
    };
    anotherFunc(); // called
  }
};

obj.sing();
```

## 3 ways fix

1. arrow functions (ES6)

```js
const obj = {
  name: 'Billy',
  sing() {
    console.log('a', this); // a {name: "Billy", sing: ƒ}
    var anotherFunc = () => {
      console.log('b', this); // b {name: "Billy", sing: ƒ}
    };
    anotherFunc(); // called
  }
};

obj.sing();
```

2. bind()

```js
const obj = {
  name: 'Billy',
  sing() {
    console.log('a', this); // a {name: "Billy", sing: ƒ}
    var anotherFunc = function() {
      console.log('b', this); // b {name: "Billy", sing: ƒ}
    };
    return anotherFunc.bind(this);
  }
};

obj.sing()();
```

3. self

```js
const obj = {
  name: 'Billy',
  sing() {
    console.log('a', this); // a {name: "Billy", sing: ƒ}
    var self = this;
    var anotherFunc = function() {
      console.log('b', self); // b {name: "Billy", sing: ƒ}
    };
    return anotherFunc;
  }
};

obj.sing()();
```
