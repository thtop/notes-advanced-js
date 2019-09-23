# Composition vs Inheritance

- Composition

  - smaller pieces that are combined to create something bigger.
  - more stable as well as easier to change in the future.

- Inheritance
  - superclass (very general)
    - subclass
      - overriding
  - the future especially with so many unknowns and humans unable to predict the future and all the changes that we might need to make to a program it becomes really difficult.

# Composition

```js
/*
- what it has

*/

function getAttack(character) {
    return Object.assign({}, character, { arrackFn: () => {}})
}

function Elf(name, weapon, type) {
    let elf = {
        name,
        weapon,
        type
    };
    return getAttact(elf);
}

// compose
Elf = attack() + sleep();
Ogre = attack() + makeFort() + sleep()

// Amazon ===
const user = {
    name: 'Kim',
    active: true,
    cart: [],
    purchases: []
}

const compose = (f, g) (...args) => f(g(...args));

function purchaseItem(...fns) {
    return fns.reduce(compose);
}

purchaseItem(
    emptyCart,
    buyItem,
    applyTaxToItems,
    addItemIoCart,
)(user, { name: 'laptop', price: 200})

function addItemToCart(user, item) {
    amazonHistory.push(user);
    const updateCart = user.cart.concat(item);
    return Object.assign({}, user, { cart: updateCart});
}

//...

```

---

# Inheritance

```js
/*
- what it is
    - Tight Coupling
    - Fragile Base Class Problem
    - Hierarchy

User
  Character
    Elf
    Ogre

Update

User
  Watcher
  Character
    Elf
        Junior Elf --> only sleep
    Ogre
*/
class Character {
  constructor(name, weapon) {
    this.name = name;
    this.weapon = weapon;
  }
  attack() {
    return 'atack with ' + this.weapon;
  }
  //slepp() {} // effects into other
}

class Elf extends Charcter {
  consttructor(name, weapon, type) {
    super(name, weapon);
    console.log('what am i?', this);
    this.type = type;
  }
}

class Ogre extends Character {
  constructor(name, weapon, color) {
    supper(name, weapon);
    this.color = color;
  }
}
//...
```
