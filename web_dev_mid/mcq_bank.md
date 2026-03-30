# MCQ Bank (Web Dev Mid)

> Pick 9 random ones to simulate your exam. Answers at the end.

## A) JS Basics
1) Which is block-scoped?  
A) var B) let C) both var/let D) none

2) `typeof null` is:  
A) "null" B) "object" C) "undefined" D) "number"

3) Which is strict equality?  
A) == B) = C) === D) !==

4) Output?
```js
console.log("5" + 2);
```
A) 7 B) "7" C) "52" D) error

5) Output?
```js
console.log("5" - 2);
```
A) 3 B) "3" C) "52" D) NaN

6) `NaN` stands for:  
A) Negative a Number B) Not a Number C) Null a Number D) New a Number

7) Output?
```js
console.log(typeof NaN);
```
A) "NaN" B) "number" C) "undefined" D) "object"

8) Which statement about `const` is true?  
A) can't change object properties  
B) can't reassign variable reference  
C) same as let  
D) only for numbers

9) What is the default value of an uninitialized variable declared with `let`?  
A) null B) 0 C) undefined D) ""

## B) Arrays
10) Which adds to end of array?  
A) pop B) push C) shift D) slice

11) Which removes from end?  
A) pop B) push C) unshift D) map

12) `map` returns:  
A) first matching item  
B) new array of same length  
C) modifies original only  
D) boolean

13) `filter` returns:  
A) new array (maybe shorter)  
B) single value  
C) index  
D) string

14) Output?
```js
[1,2,3].includes(2)
```
A) true B) false C) 2 D) error

## C) Functions & Scope
15) Function declaration is hoisted?  
A) yes B) no C) only arrow D) only anonymous

16) Arrow functions have their own `this`?  
A) yes B) no C) only in classes D) only in browsers

17) What’s the output?
```js
function f(){ console.log(a); }
let a = 10;
f();
```
A) 10 B) undefined C) error D) null

## D) Objects + OOP
18) Access property `age` in object `u`?  
A) u(age) B) u->age C) u.age D) u:age

19) In `obj.method()`, `this` refers to:  
A) global window  
B) obj  
C) method function itself  
D) undefined always

20) `new` does what?  
A) calls function without parentheses  
B) creates object + sets `this` + links prototype  
C) turns function into arrow  
D) removes prototype

## E) DOM + Events (Client Side)
21) Select first element with class `box`:  
A) getElementById("box")  
B) querySelector(".box")  
C) querySelectorAll(".box")  
D) getElementsByTagName(".box")

22) Prevent form refresh on submit:  
A) stop() B) e.preventDefault() C) return false always D) clearInterval()

23) Change text of element `p`:  
A) p.value="x" B) p.textContent="x" C) p.src="x" D) p.href="x"

24) Add click handler:  
A) button.onClick(fn)  
B) button.addEventListener("click", fn)  
C) button.add("click", fn)  
D) button.listen("click", fn)

---

## Answer Key
1) B  
2) B  
3) C  
4) C  
5) A  
6) B  
7) B  
8) B  
9) C  
10) B  
11) A  
12) B  
13) A  
14) A  
15) A  
16) B  
17) A  
18) C  
19) B  
20) B  
21) B  
22) B  
23) B  
24) B
