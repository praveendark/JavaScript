# JavaScript

# script tag
The script tag is used to embed a client-side script (JavaScript). 
The script element either contains scripting statements, or it points to an external script file through the src attribute.

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
# 1 this
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
