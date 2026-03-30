# JavaScript Core Concepts (Midterm)

## 1) Where JS runs
- Browser: script in HTML or external file.
```html
<script src="app.js" defer></script>
```
- `defer` runs after HTML is parsed.

## 2) Variables
- `let` (reassignable), `const` (not reassignable), avoid `var`.

```js
let x = 1; x = 2;
const y = 5; // y = 6 -> error
```

## 3) Data types
- Primitive: `string`, `number`, `boolean`, `undefined`, `null`, `bigint`, `symbol`
- Non-primitive: `object` (includes arrays, functions)

```js
typeof "hi" // "string"
typeof 10   // "number"
typeof null // "object" (weird JS behavior)
typeof []   // "object"
```

## 4) Operators + comparisons
- `===` strict (use this), `==` loose (avoid)
```js
"5" == 5  // true
"5" === 5 // false
```

## 5) Conditionals
```js
if (score >= 50) pass = true;
else pass = false;
```

## 6) Loops
```js
for (let i = 0; i < arr.length; i++) {}
for (const item of arr) {}      // arrays
for (const key in obj) {}       // object keys
```

## 7) Functions
- Declaration vs expression vs arrow

```js
function add(a,b){ return a+b; }

const add2 = function(a,b){ return a+b; };

const add3 = (a,b) => a + b;
```

## 8) Scope
- `let/const` are **block scoped**
```js
if (true) { let a = 1; }
// console.log(a) -> error
```

## 9) Arrays (high yield)
- Common methods:
  - `push/pop`, `shift/unshift`, `slice`, `splice`
  - `map`, `filter`, `find`, `reduce`, `includes`

```js
const nums = [1,2,3,4];
const evens = nums.filter(n => n % 2 === 0); // [2,4]
const squares = nums.map(n => n*n);          // [1,4,9,16]
```

## 10) Objects + JSON
```js
const user = { name: "Ali", age: 20 };
user.age;        // 20
user["name"];    // "Ali"
```

JSON:
```js
JSON.stringify(user); // to string
JSON.parse('{"a":1}'); // to object
```

## 11) Errors & common pitfalls
- Floating point:
```js
0.1 + 0.2 === 0.3 // false
```
- `NaN`:
```js
Number("x") // NaN
typeof NaN  // "number"
```
