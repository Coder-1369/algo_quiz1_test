# JavaScript on the Client Side (DOM + Events)

## 1) DOM selection
```js
document.getElementById("title");
document.querySelector(".card");     // first match
document.querySelectorAll("li");     // NodeList
```

## 2) Read / change content
```js
el.textContent = "Hello";
el.innerHTML = "<b>Hello</b>"; // use carefully
```

## 3) Attributes + classes
```js
img.setAttribute("src", "a.png");
el.classList.add("active");
el.classList.remove("active");
el.classList.toggle("active");
```

## 4) Events
```js
button.addEventListener("click", () => {
  console.log("clicked");
});
```

### Event object
```js
form.addEventListener("submit", (e) => {
  e.preventDefault(); // stop page refresh
});
```

## 5) Forms
```js
const email = document.querySelector("#email").value;
```

Simple validation example:
```js
if (!email.includes("@")) {
  error.textContent = "Invalid email";
}
```

## 6) Create / append elements
```js
const li = document.createElement("li");
li.textContent = "New item";
list.appendChild(li);
```

## 7) Timing
```js
setTimeout(() => console.log("once"), 1000);
const id = setInterval(() => console.log("repeat"), 1000);
clearInterval(id);
```
