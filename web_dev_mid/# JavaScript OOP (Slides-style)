# JavaScript OOP (Slides-style)

## 1) Objects and methods
```js
const car = {
  brand: "Toyota",
  drive() { return "vroom"; }
};
```

## 2) Constructor function + `new`
```js
function Person(name) {
  this.name = name;
}
const p = new Person("Sara");
```

## 3) Prototypes
```js
Person.prototype.sayHi = function() {
  return "Hi " + this.name;
};
p.sayHi(); // "Hi Sara"
```

## 4) Classes (syntactic sugar over prototypes)
```js
class Person2 {
  constructor(name) { this.name = name; }
  sayHi() { return "Hi " + this.name; }
}
```

## 5) `this` rules (very common MCQ)
- Method call: `obj.method()` → `this = obj`
- Plain function call: `this` is `undefined` in strict mode (or window in non-strict)
- Arrow functions: `this` is **lexical** (inherits from outer scope)

```js
const obj = {
  x: 10,
  normal() { return this.x; },
  arrow: () => this.x
};
obj.normal(); // 10
obj.arrow();  // usually undefined (depends on outer this)
```
