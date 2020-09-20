# JavaScript

# script tag
The script tag is used to embed a client-side script (JavaScript). 
The script element either contains scripting statements, or it points to an external script file through the src attribute.


# Running Javascript


## script tag


The script tag is used to embed a client-side script (JavaScript). The script element either contains scripting statements, or it points to an external script file through the src attribute.

``` js
<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
```

## Browser console

Js also can be writter on the console in the web browser

``` js
function add(a, b=20) {
  return a + b;
}
add(25)
```

## Link external file

Or it can be writter in another seperate file  and can be called in  whatever file we want

``` js
<script src="script.js"></script>
```

# Variables

## Declarations
Declarations are used to declare varriables in js and there are of mainly 3 types

### Var
Var declarations are globally scoped or function/locally scoped.
The scope is global when a var variable is declared outside a function. This means that any variable that is declared with var outside a function block is available for use in the whole window.

var is function scoped when it is declared within a function. This means that it is available and can be accessed only within that function.
``` js
    var tester = "hey hi";
    
    function newFunction() {
        var hello = "hello";
    }
    console.log(hello); //error:undefined
```

var variables can be also re-declared/updated
### let

Just like var,  a variable declared with let can be updated within its scope. Unlike var, a let variable cannot be re-declared within its scope. So while this will work:

``` js
  let greeting = "say Hi";
  let greeting = "say Hello instead"; // error: Identifier 'greeting' has already been declared
```
### const

Variables declared with the const maintain constant values. const declarations share some similarities with let declarations.
Like let declarations, const declarations can only be accessed within the block they were declared. it cannot be re-declared/  updated

```js
const greeting = "say Hi";
greeting = "say Hello instead";// error: Assignment to constant variable. 
```    

## Scope

### Global

A variable declared outside a function, becomes GLOBAL. A global variable has global scope: All scripts and functions on a web page can access it

### Function
Each function creates a new scope. Scope determines the accessibility (visibility) of these variables. Variables defined inside a function are not accessible (visible) from outside the function.

### Block

A block scope is the area within if, switch conditions or for and while loops. const and let keywords allow  to declare variables in the block scope, which means those variables exist only within the corresponding block

# Data Types and Data structures

##  Primitive Types
Data that is not an object and has no methods and below are the primitve data types in js
###    undefined
The undefined type is a primitive type that has one special value undefined . By default, when a variable is declared but not initialized, it is assigned the value of undefined .

```js
var undef; //If a value is never assigned, any output will be 'undefined'
```

###   Boolean
These are yes/no type

```js
var isReading = true; //Yes, I'm reading
var isSleeping = false; //No, I'm not sleeping
```
###    Number
Number type
```js
var num = 25; //Integer
var flo = 80.5; //Floating-point number
var exp = 4.25e+6; //Exponential notation, this equates to 4250000
```
###    BigInt
The BigInt type is a numeric primitive in JavaScript that can represent integers with arbitrary precision

```js
const theBiggestInt = 9007199254740991n
const alsoHuge = BigInt(9007199254740991) // 9007199254740991n
const hugeString = BigInt("9007199254740991") // 9007199254740991n
```
###    String

String type
```js
var strSingle = 'John'; //String with single quotes
var strDouble = "Bob"; //String with double quotes
```
###    Symbol
To create a new primitive symbol, you write Symbol() with an optional string as its description:
Once you create a symbol, its value is kept private and for internal use
```js
let sym1 = Symbol()
let sym2 = Symbol('foo')
//cant create a symbol object like this
let sym = new Symbol()  // TypeError
//it can be archieved by
let sym = Symbol('foo')
typeof sym      // "symbol" 
let symObj = Object(sym)
typeof symObj   // "object"
```
##  null
In JavaScript null is "nothing". It is supposed to be something that doesn't exist. Unfortunately, in JavaScript, the data type of null is an object
```js
var noValue = null; //Null meaning that it is has no value, not the same as 0 or ""

```
##  Object
An object contains properties, defined as a key-value pair. A property key (name) is always a string, but the value can be any data type, like strings, numbers, booleans, or complex data types like arrays, function and other objects

```js
var emptyObject = {};
var person = {"name": "Clark", "surname": "Kent", "age": "36"}; 
var car = { 
	model: "BMW X3", 
	color: "white",
	doors: 5
}
```
##  Function

```js
var func = function() { //Calling the function: func();
  alert("Code excuted"); //Outputs: Code executed
}

var funcVar = function(amount) { //Calling the function: funcVar(6); 
  alert("Code excuted " + amount + " times"); //Outputs: Code executed 6 times (if input was 6)
}
```

# Data Structures
Data structures, at a high level, are techniques for storing and organizing data that make it easier to modify, navigate, and access. Data structures determine how data is collected, the functions we can use to access it, and the relationships between data
##  Array
An array is a special variable, which can hold more than one value at a time.
### creating an array
```js
var cars = [
  "Saab",
  "Volvo",
  "BMW"
];
var cars = ["Saab", "Volvo", "BMW"];

```
### Array methods
>>concat()

The concat() method is used to join two or more arrays.
```js
var hege = ["Cecilie", "Lone"];
var stale = ["Emil", "Tobias", "Linus"];
var children = hege.concat(stale);
```
>> filter()

The filter() method creates an array filled with all array elements that pass a test (provided as a function).filter() does not change the original array.

```js
var ages = [32, 33, 16, 40];

function checkAdult(age) {
  return age >= 18;
}

console.log(ages.filter(checkAdult))
```

>> find()

The find() method returns the value of the first element in an array that pass a test (provided as a function).

The find() method executes the function once for each element present in the array:

If it finds an array element where the function returns a true value, find() returns the value of that array element (and does not check the remaining values)
Otherwise it returns undefined. find() does not execute the function for empty arrays. find() does not change the original array.

```js
var ages = [3, 10, 18, 20];

function checkAdult(age) {
  return age >= 18;
}

console.log(ages.find(checkAdult);)
```

>>include()

The includes() method determines whether an array contains a specified element.
This method returns true if the array contains the element, and false if not. The includes() method is case sensitive.

```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var n = fruits.includes("Mango");
console.log(n) //true
```

>>from()

The Array.from() method returns an Array object from any object with a length property or an iterable object

```js
var myArr = Array.from("ABCDEFG");
console.log(myArr) //A,B,C,D,E,F,G
```

>> indexof()

The indexOf() method searches the array for the specified item, and returns its position.

The search will start at the specified position, or at the beginning if no start position is specified, and end the search at the end of the array.

Returns -1 if the item is not found.

If the item is present more than once, the indexOf method returns the position of the first occurence.

```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var a = fruits.indexOf("Apple"); 
console.log(a) //2
```
<!-- ##  Map/Weak Map
##  set/Weak set -->

# Type Conversion

## Explicite Conversion 

Converting data types as per our requirement
For example, String conversion
```js
let value = true;
alert(typeof value); // boolean

value = String(value); // now value is a string "true"
alert(typeof value); // string
```
## implicite Conversion

Convert automatically to the required data type.Most of the time, operators and functions automatically convert the values given to them to the right type.
For example, alert automatically converts any value to a string to show it

# Equality

## == vs ===

Triple equal -> Strict equality compares two values for equality. Neither value is implicitly converted to some other value before being compared. If the values have different types, the values are considered unequal.

```js
var num = 0;
var obj = new String('0');

console.log(num === num); // true
console.log(num === obj); // false
```

Double equal -> Loose equality compares two values for equality, after converting both values to a common type. After conversions (one or both sides may undergo conversions), the final equality comparison is performed exactly as === performs

```js
var num = 0;
var obj = new String('0');

console.log(num === num); // true
console.log(num === obj); // true
```

# Loops

## break/continue
## for..in
for/in loops are used to find something that are to be finded from the collection of data we have

```js
var person = {fname:"John", lname:"Doe", age:25};

var text = "";
var x;
for (x in person) {
  text += person[x] + " ";
} //output : joe Doe 25
```
## for..of

The for...of statement creates a loop iterating over iterable objects in the array

```js
const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}
//  output: "a"
//  output: "b"
//  output: "c"
```
# Control Flow

##  try/catch/throw

It is used for exception handling.

The try statement lets you test a block of code for errors.

The catch statement lets you handle the error.

The throw statement lets you create custom errors.

The finally statement lets you execute code, after try and catch, regardless of the result.

```js
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
finally {
  Block of code to be executed regardless of the try / catch result
}
```

# Expressions & Operaters


##  Comparision Operaters
### = = (Equal)

Checks if the value of two operands are equal or not, if yes, then the condition becomes true.

Ex: (A == B) is not true.

### != (Not Equal)

Checks if the value of two operands are equal or not, if the values are not equal, then the condition becomes true.

Ex: (A != B) is true.

### > (Greater than)

Checks if the value of the left operand is greater than the value of the right operand, if yes, then the condition becomes true.

Ex: (A > B) is not true.

### < (Less than)

Checks if the value of the left operand is less than the value of the right operand, if yes, then the condition becomes true.

Ex: (A < B) is true.

# Functions

## Arrow Functions

Arrow functions allow us to write shorter function syntax:

```js
//Normal
hello = function() {
  return "Hello World!";
}
//Arrow
hello = () => {
  return "Hello World!";
}
//or 
hello = () => "Hello World!";
//with parameter
hello = val => "Hello " + val;
```

### this in arrow fucntion
The handling of this is also different in arrow functions compared to regular functions.
In short, with arrow functions there are no binding of this.
In regular functions the this keyword represented the object that called the function, which could be the window, the document, a button or whatever.
With arrow functions the this keyword always represents the object that defined the arrow function.

```js
//Regular Function:
//here when it run first it will be a window object and when a buton click ,it  will be of btn object
hello = function() {
  document.getElementById("demo").innerHTML += this;
}
//The window object calls the function:
window.addEventListener("load", hello);
//A button object calls the function:
document.getElementById("btn").addEventListener("click", hello)
;

//Arrow Function:
//here this  keyword represents the object that owns the function, no matter who calls the function.
hello = () => {
  document.getElementById("demo").innerHTML += this;
}
//The window object calls the function:
window.addEventListener("load", hello);
//A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);

```

``` js
<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
```
# Currying
Currying is a technique of evaluating function with multiple arguments, into sequence of functions with single argument.In other words, when a function, instead of taking all arguments at one time, takes the first one and return a new function that takes the second one and returns a new function which takes the third one, and so forth, until all arguments have been fulfilled.

``` js
     function Myfunction(a) {
        return (b) => {
           return (c) => {
             return a * b * c
             }
            }
         }
```
# Closure
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time.

``` js
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() { // displayName() is the inner function, a closure
    alert(name); // use variable declared in the parent function
  }
  displayName();
}
init();
```
# 1. this
The JavaScript this keyword refers to the object it belongs to.
In a method, this refers to the owner object.
Alone, this refers to the global object.
In a function, this refers to the global object.
In an event, this refers to the element that received the event.
Methods like call(), and apply() can refer this to any object.

``` js
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

## 1.1 this in method

``` js
var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

## 1.2 Explicit Function Binding

The call() and apply() methods are predefined JavaScript methods.

They can both be used to call an object method with another object as argument.

``` js
var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
person1.fullName.call(person2);  // Will return "John Doe"
```
# Prototype

The prototype is an object that is associated with every functions and objects by default in JavaScript, where function's prototype property is accessible and modifiable and object's prototype property (aka attribute) is not visible.
The prototype object is special type of enumerable object to which additional properties can be attached to it which will be shared across all the instances of it's constructor function.

``` js
function Student() {
    this.name = 'John';
    this.gender = 'M';
}

Student.prototype.age = 15;

var studObj1 = new Student();
alert(studObj1.age); // 15

var studObj2 = new Student();
alert(studObj2.age); // 15
```

# Prototype Inheritance
All JavaScript objects inherit properties and methods from a prototype:

Date objects inherit from Date.prototype
Array objects inherit from Array.prototype
Person objects inherit from Person.prototype
The Object.prototype is on the top of the prototype inheritance chain:

Date objects, Array objects, and Person objects inherit from Object.prototype.

# Class
A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.

The constructor method is called each time the class object is initialized.

``` js
class Car {
  constructor(brand) {
    this.carname = brand;
  }
}
mycar = new Car("Ford");
```
# Event Loop

The Event Loop has one simple job — to monitor the Call Stack and the Callback Queue. If the Call Stack is empty, it will take the first event from the queue and will push it to the Call Stack, which effectively runs it.

# Asynchronous Javascript
## setTimeout()
The setTimeout() method calls a function or evaluates an expression after a specified number of milliseconds.
``` js
<script>
function myFunction() {
  setTimeout(function(){ alert("Hello"); }, 3000);
}
</script>
```
## setInterval()
The setInterval() method calls a function or evaluates an expression at specified intervals (in milliseconds).

``` js
<script>
function myFunction() {
  setInterval(function(){ alert("Hello"); }, 3000);
}
</script>
```
## Callback Function
A JavaScript Callback Function is a function that is passed as a parameter to another JavaScript function, and the callback function is run inside of the function it was passed into

``` js
function functionOne(x) { return x; };

function functionTwo(var1) {
    // some code
}

functionTwo(functionOne);
```
## Promise
A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (e.g., a network error occurred). A promise may be in one of 3 possible states: fulfilled, rejected, or pending.

## async/await
An async function is a function declared with the async keyword. Async functions are instances of the AsyncFunction constructor, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.
# Web API

## Ambient Light Events
The ambient light events are a handy way to make a web page or an application aware of any change in the light intensity. It allows them to react to such a change, for example by changing the color contrast of the User Interface (UI) or by changing the exposure necessary to take a picture.
This event can be captured at the window object level by using the addEventListener method (using the devicelight event name) or by attaching an event handler to the window.ondevicelight property.

Once captured, the event object gives access to the light intensity expressed in lux through the DeviceLightEvent.value property.
```js
if ('ondevicelight' in window) {
  window.addEventListener('devicelight', function(event) {
    var body = document.querySelector('body');
    if (event.value < 50) {
      body.classList.add('darklight');
      body.classList.remove('brightlight');
    } else {
      body.classList.add('brightlight');
      body.classList.remove('darklight');
    }
  });
} else {
  console.log('devicelight event not supported');
}
```
## Background Tasks API
The Cooperative Scheduling of Background Tasks API (also referred to as the Background Tasks API or simply the requestIdleCallback() API) provides the ability to queue tasks to be executed automatically by the user agent when it determines that there is free time to do so.

## Battery Status API
The Battery Status API, more often referred to as the Battery API, provides information about the system's battery charge level and lets you be notified by events that are sent when the battery level or charging status change. This can be used to adjust your app's resource usage to reduce battery drain when the battery is low, or to save changes before the battery runs out in order to prevent data loss.
## Bluetooth API

## BroadcastChannel API
By creating a BroadcastChannel object, you can receive any messages that are posted to it. You don't have to maintain a reference to the frames or workers you wish to communicate with: they can “subscribe” to a particular channel by constructing their own BroadcastChannel with the same name, and have bi-directional communication between all of them.
The Web Bluetooth API provides the ability to connect and interact with Bluetooth Low Energy peripherals.

###Creating or joining a channel
A client joins a broadcast channel by creating a BroadcastChannel object. Its constructor takes one single parameter: the name of the channel. If it is the first to connect to that broadcast channel name, the underlying channel is created.

// Connection to a broadcast channel
const bc = new BroadcastChannel('test_channel');
###Sending a message
It is enough to call the postMessage() method on the created BroadcastChannel object, which takes any object as an argument. An example string message:

// Example of sending of a very simple message
bc.postMessage('This is a test message.');
Any kind of object can be sent, not just a DOMString.

The API doesn't associate any semantics to messages, so it is up to the code to know what kind of messages to expect and what to do with them.

###Receiving a message
When a message is posted, a message event is dispatched to each BroadcastChannel object connected to this channel. A function can be run for this event with the onmessage event handler:

// A handler that only logs the event to the console:
bc.onmessage = function (ev) { console.log(ev); }
###Disconnecting a channel
To leave a channel, call the close() method on the object. This disconnects the object from the underlying channel, allowing garbage collection.

// Disconnect the channel
bc.close();
 
## CSS Counter Styles
The CSS Counter Styles module allows to define custom counter styles

## Channel Messaging API

The Channel Messaging API allows two separate scripts running in different browsing contexts attached to the same document (e.g., two IFrames, or the main document and an IFrame, two documents via a SharedWorker, or two workers) to communicate directly, passing messages between one another through two-way channels (or pipes) with a port at each end.

## Console API
The Console API provides functionality to allow developers to perform debugging tasks, such as logging messages or the values of variables at set points in your code, or timing how long an operation takes to complete.

## Content Index API

The Content Index API allows developers to register their offline enabled content with the browser.
As it stands, offline web content is not easily discoverable by users. Content indexing allows developers to tell the browser about their specific offline content. This allows users to discover and view what is available, whilst giving developers the ability to add and manage this content. Examples could be a news website prefetching the latest articles in the background, or a content streaming app registering downloaded content.

## Document Object Model (DOM)
The Document Object Model (DOM) connects web pages to scripts or programming languages by representing the structure of a document—such as the HTML representing a web page—in memory

## Fetch API
The Fetch API provides an interface for fetching resources (including across the network). It will seem familiar to anyone who has used XMLHttpRequest, but the new API provides a more powerful and flexible feature set.

## Fullscreen API

he Fullscreen API adds methods to present a specific Element (and its descendants) in full-screen mode. This makes it possible to present desired content—such as an online game—using the user's entire screen, removing all browser user interface elements and other applications from the screen until full-screen mode is shut off.

## Geolocation API
The Geolocation API allows the user to provide their location to web applications if they so desire. For privacy reasons, the user is asked for permission to report location information.

Geolocation.getCurrentPosition(): Retrieves the device's current location.
Geolocation.watchPosition(): Registers a handler function that will be called automatically each time the position of the device changes, returning the updated location.

## HTML Drag and Drop

HTML Drag and Drop interfaces enable applications to use drag-and-drop features in browsers. The user may select draggable elements with a mouse, drag those elements to a droppable element, and drop them by releasing the mouse button. A translucent representation of the draggable elements follows the pointer during the drag operation.

## Performance API
The High Resolution Time standard defines a Performance interface that supports client-side latency measurements within applications. The Performance interfaces are considered high resolution because they are accurate to a thousandth of a millisecond (subject to hardware or software constraints). The interfaces support a number of use cases including calculating frame-rates (potentially important in animations) and benchmarking (such as the time to load a resource).

## History API
The DOM Window object provides access to the browser's session history (not to be confused for WebExtensions history) through the history object. It exposes useful methods and properties that let you navigate back and forth through the user's history, and manipulate the contents of the history stack.Moving backward and forward through the user's history is done using the back(), forward(), and go() methods.
