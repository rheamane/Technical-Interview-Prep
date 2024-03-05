#webdevelopment #frontend

### Adding variables to the page
- Using append
```js
const body = document.body
body.append("Hello World", "Bye")
```
- Using create element (for elements and not just strings)
```js
const body = document.body
const div = document.createElement("div") // only creates the div and doesnt add it to the page
div.innerText = "Hello World"
div.textContent = "Hello World 2"
body.append(div) // adds div to the page
```

- To use HTML inside the div tag - use innerHTML
```js
const body = document.body
const div = document.createElement("div")
div.innerHTML = "<strong> Hello World 2 </strong>"

body.append(div)
```
 also
 ```js
 const body = document.body
const div = document.createElement("div")
const strong = document.createElement("strong")
strong.innerText = "Hello World 2"
div.append(strong)

body.append(div)
```

### Removing elements
- Using the remove function
```js
const body = document.body
const div = document.querySelector("div")
const spanHi = document.querySelector("#hi");
const spanBye = document.querySelector("#bye")

spanBye.remove()
// also
div.removeChild(spanHi)
```

### Modifying elements
- Can use getAttribute and setAttribute
```js
const body = document.body
const div = document.querySelector("div")
const spanHi = document.querySelector("#hi");
const spanBye = document.querySelector("#bye")

// Set attribute
console.log(spanHi.setAttribute("id","abcasbc"))
spanBye.id = "abhcks"

// Get attribute
spanHi.getAttribute("title")
spanHi.id

// remove attribute
spanHi.removeAttribute("id")

```

### Making your own attributes
```html
// use datasets
<span id = "hi" data-test="this is a test"> hello </span>
<span id = "bye"> Bye </span>

```
```js
const body = document.body
const div = document.querySelector("div")
const spanHi = document.querySelector("#hi");
const spanBye = document.querySelector("#bye")

console.log(spanHi.dataset.test)
spanHi.dataset.newName = "hi"
```

### Classes
```js
const body = document.body
const div = document.querySelector("div")
const spanHi = document.querySelector("#hi");
const spanBye = document.querySelector("#bye")

spanHi.classList.add("new-class")
spanHi.classList.remove("hi1")
spanHi.classList.toggle("hi2")
spanHi.classList.toggle("hi3", false) // to add or remove using boolean
```

### Modifying style 
```js
spanHi.style.color = "red"
spanHi.style.backgroundColor = "pink"
```


# Event Listeners

Basic index.html 
```html
<html>
<body>
	<div class= "grandparent">
		<div class = "parent">
			<div class = "child"></div>
		</div>
	</div>
</body>
</html>
```

script.js
```js
const grandparent = document.querySelector(".grandparent")
const parent = document.querySelector(".parent")
const child = document.querySelector(".child")

// 
grandparent.addEventListener('click', e => {
	console.log("Grandparent 1")
}, {capture: true})

parent.addEventListener('click', e => {
	console.log("Parent 1")
})

child.addEventListener('click', e => {
	console.log("Child 1")
})

document.addEventListener('click', e=>{
	console.log("Document 1")
})
```

- Capture goes from outside to inside 
- Bubble goes from inside to outside

- stopPropogation stops the capturing and bubbling
```js
e.stopPropogation()
``` 

- Run event once, and never again
```js
parent.addEventListener('click', e => {
	console.log("Parent 1")
}, {once: true})
```

```js
// To remove an event listener altogether
parent.removeEventListener()
```
