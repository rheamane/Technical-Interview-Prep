#webdevelopment #javascript

- [x] Comments
- [x] Variables and Basic Data Types
- [x] Conditionals (If/Else, Boolean types)
- [x] Loops 
- [x] For... in, and For...of 
- [x] Objects 
- [x] Functions
- [x] Expressions and Operators

## Comments
```javascript
// this is a single line comment
/* this is
a multi-line comment */
```

## Variables

There are 4 ways to declare variables:
- Automatically
- Using var
- Using let
- Using const - cant change the value once declared

```js
// Automatic initialization
x = 3;
y = 4; 
z = x+y;
```

```js
// using var
var x = 3;

// using let
let y = 6;

// Using const
cont z = 19;
```

= : Assignment operator
== : equals operator

Variables can hold a number of data type, most commonly numbers and text strings.
[!tip] Numbers enclosed in quotes will be considered to be a text string. 

- a variable declared without a value will have the value of undefined
- A variable declared with var, if redeclared will not lose its value
```js
 let carPool;
 var number = 9;
 var number;
```
 the var number will still be equal to 9

Using the + operator for strings and numbers. 
Numbers will be added and strings will be concatenated

```js
let x = 9;
let y = 1
 z = x + y;
 // z = 10;

let a = "hello";
let b = "world";
let c = a + b;
// c = "helloworld"
```

Java script considers $ and _ to be valid identifiers. 

## Data Types

- Java Script has 8 basic datatypes : String, Number, Bigint, Boolean, Undefined, Null, Symbol and Object
- The Object datatype can have an array, an object or a date

[!note]- A JavaScript variable can have any datatype.

- When adding a number and a string the compiler will consider the number to be a string and concatenate them. 
- JavaScript has dynamic datatypes therefore same variables can have different datatypes. 
- All numbers in JavaScript are saved as floating point numbers. 

Arrays:
```js
// Declaration of an Array in JS
const car = ["A", "B", "C"];
```
- Array indexing starts with 0

Objects:
```js
// Declaration of an Object in JS
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};  
```
- Objects are name : value pairs, separated by commas.

typeOf operator can be used to find the type of the variable. 
A variable without a value has type undefined. The value is also undefined
```js
let car; // value is undefined
```
```
house = undefined;
```
- An empty value is not undefined
```js
// this value is empty not undefined
let variable = "";

// this value is undefined
variable = undefined;
```

## Conditionals

#### IF
```js
if (a < 5){
	b = 1;
}
```

#### Else
```js
if (a < 5){
	b = 1
}else{
	b = 5;
}
```

#### Else if
```js
if (a < 5){
	b = 1
}
else if (a > 9){
	b = 5;
} 
else{
	 b = 0;
}
```

#### Switch 
```js
switch(true){
	case "x":
		// code
		break;
	case "y":
		// code
		break;
	default:
		// code
}
```
- break keywords breaks out of the switch block
- default keyword gives the code to run if no match is found

## Booleans

true/false
- Boolean() function which decides whether a value is true or false
```js
let x = true;
Boolean(x)
```

- Everything with a value is True. Ex: "a", 3.14
- Everything without a value is False. Ex: undefined, NULL, 0 , ""

=== : Strict Equality
- If the operands are of different types, return `false`.
- If both operands are objects, return `true` only if they refer to the same object.
- If both operands are `null` or both operands are `undefined`, return `true`
- If either operand is `NaN`, return `false`.
- Otherwise, compare the two operand's values:
    - Numbers must have the same numeric values. `+0` and `-0` are considered to be the same value.
    - Strings must have the same characters in the same order.
    - Booleans must be both `true` or both `false`.

## Loops

#### For 
- This for loops through a block of code a number of times.
```js
for(let i = 0; i < length; i++){
	// code block
}
```

#### For in
- The for in loop goes through the properties of an object
```js
const person = {fname: john, lname: doe, age: 25}
let text = "";
for (let x in person){
	text += person[x];
}
```

#### For of
- The for of loop iterates through values of an iterable object
- Lets you iterate over iterable data structures like Arrays, Strings, Maps and Objects
```js
// with an array
const cars = ["A", "B", "C"];
let text = "";
for (let x of cars){
	text += x;
}
```

```js
// with a string
let str = helloworld;

let text = "";
for (let x of str){
	text += x;
}
```

#### While
- The while loop executes a block of code as long as the condition is true. 
```js
while ( i < 0){
	z += i;
	i ++;
}
```

#### Do While
- Loop will be executed atleast once even if the condition is false
```js
do{
	z += i;
	i ++;
}while(i < 0)
```


- The `break` statement "jumps out" of a loop.
- The `continue` statement "jumps over" one iteration in the loop.

## Functions 

- A JavaScript function is a block of code designed to perform a particular task.
- A JavaScript function is executed when "something" invokes it (calls it).

```js
function myfunc(p1, p2){
	return p1 *p2;
}
```

- Variables declared within a JavaScript function, become **LOCAL** to the function. Local variables can only be accessed from within the function.

## Expressions and Operators

- An expression is a valid unit of code which resolves to a value

#### Comparison Operator
| Operator | Description |
| ---------- | ------------ |
| ==  Equals | Returns `true` if the operands are equal. |
| ! = Not Equals  | Returns `true` if the operands are not equal |
| === Strict Equals | Returns `true` if the operands are equal and of the same type. |
| !== Strict not equal | Returns `true` if the operands are of the same type but not equal, or are of different type. |
|



## Objects

An object is anything that has state (variables) and behavior (methods).

#### Declaring an Object
```js
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};  
```

#### Accessing an Object
```js
person.firstName;
// or 
person["lastName"];
```
