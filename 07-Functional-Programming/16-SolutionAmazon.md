# Solution: Amazon

```js
// Amazon shopping
const user = {
  name: 'Kim',
  active: true,
  carts: [{ name: 'Pen', price: 20 }],
  purchases: []
};

let amazonHistory = [];
function getUserState() {}
function goBack() {}
function goForword() {}

const compose = (f, g) => (...args) => f(g(...args));

// function purchaseItem(user, item) {
//   //return Object.assign({}, user, { durchases: item });
//   const purchases = [item];
//   return { ...user, purchases };
// }

function purchaseItem(...fns) {
  return fns.reduce(compose);
}

function addItemToCart(user, item) {
  amazonHistory.push(user);
  const cart = item;
  const carts = [...user.carts, cart];
  return { ...user, carts };
}

function applyTaxToItems(user) {
  amazonHistory.push(user);
  const taxRate = 1.3;
  const carts = user.carts.map(item => {
    return { name: item.name, price: item.price * taxRate };
  });
  return { ...user, carts };
}

function buyItem(user) {
  amazonHistory.push(user);
  const purchases = [...user.carts];
  return { ...user, purchases };
}

function emptyCart(user) {
  amazonHistory.push(user);
  return { ...user, carts: [] };
}

function refundItem() {}

//console.log(purchaseItem(user, { name: 'laptop', price: 344 }))
const result = purchaseItem(emptyCart, buyItem, applyTaxToItems, addItemToCart)(
  user,
  { name: 'laptop', price: 200 }
);

console.log(result);
console.log(amazonHistory);
```

---

## Compose

```js
// Amazon shopping
const user = {
  name: 'Kim',
  active: true,
  carts: [{ name: 'Pen', price: 20 }],
  purchases: []
};

const compose = (f, g) => (...args) => f(g(...args));

function purchaseItem(...fns) {
  return fns.reduce(compose);
}

function addItemToCart(user, item) {
  const cart = item;
  const carts = [...user.carts, cart];
  return { ...user, carts };
}

function applyTaxToItems(user) {
  const taxRate = 1.3;
  const carts = user.carts.map(item => {
    return { name: item.name, price: item.price * taxRate };
  });
  return { ...user, carts };
}

function buyItem(user) {
  const purchases = [...user.carts];
  return { ...user, purchases };
}

function emptyCart(user) {
  return { ...user, carts: [] };
}

const result = purchaseItem(emptyCart, buyItem, applyTaxToItems, addItemToCart)(
  user,
  { name: 'laptop', price: 200 }
);

console.log(result);
```

---

## Pipe

```js
// Amazon shopping
const user = {
  name: 'Kim',
  active: true,
  carts: [{ name: 'Pen', price: 20 }],
  purchases: []
};

const pipe = (f, g) => (...args) => g(f(...args));

function purchaseItem(...fns) {
  return fns.reduce(pipe);
}

function addItemToCart(user, item) {
  const cart = item;
  const carts = [...user.carts, cart];
  return { ...user, carts };
}

function applyTaxToItems(user) {
  const taxRate = 1.3;
  const carts = user.carts.map(item => {
    return { name: item.name, price: item.price * taxRate };
  });
  return { ...user, carts };
}

function buyItem(user) {
  const purchases = [...user.carts];
  return { ...user, purchases };
}

function emptyCart(user) {
  return { ...user, carts: [] };
}

const result = purchaseItem(emptyCart, buyItem, applyTaxToItems, addItemToCart)(
  user,
  { name: 'laptop', price: 200 }
);

console.log(result);
```
