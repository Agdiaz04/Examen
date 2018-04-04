1. What is a potential pitfall with using typeof bar === "object" to determine if bar is an object? How can this pitfall be avoided?
R: Null is consider an object as well, so if bar is equal to null, you will get true for that comparison, so you could also compare if bar is equal to null with an  "and"
There are other similar situations, but mostly you can avoid this situations adding some more "if's"

2. What will the code below output to the console and why?
   
```javascript
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```
R:
bar - refers to the object which has a property called "foo", which contains the value "bar"
bar - since this is assigned to "self" and they are in the same scope, it refers to the same foo
undefined - In this case "this" refers to the inner function, which by itself has no property foo
bar - In this case, the variable "self" is found within the scope of the original function, and makes reference to the external "this", therefore if it has access to the variable "foo"

3. What is the significance of wrapping the entire content of a JavaScript source file in a function block?

R: It's the equivalent in other languages ??to use a namespace, in addition to serving as a driver of the visibility of functions and variables

4. What will the code below output to the console and why?
```javascript
 (function(){
    return typeof arguments;
  })();
```
Object
R: Because in javascript all values are objects, except for primitve data (string, number, boolean, null, undefined)


5. What will the code below output to the console and why?
```javascript
  var foo = {
    bar: function() { return this.baz; },
    baz: 1
  };
  (function(){
    return typeof arguments[0]();
  })(foo.bar);
```
R: Undefined - In this case this refers to the global object, and that object doesn't have any property call "baz", therefore it returns "undefined"

6. What will the code below output to the console and why?
```javascript
  var x = 1;
  if (function f(){}) {
    x += typeof f;
  }
  x;
```
R: 1Undefined, the variable 'x' is equal to one, and the function is taken as an expression because is inside an if statement, and because f it is not defined, then the addition of x and f it turns into a string concatanation of "1" and "unfefined"

7. What will the code below output to the console and why?
```javascript
/^(ab)$/.test('(ab)')
/^aa|bb$/.test('aaxx')
```
R:
false - ^ ask to match only at the beggining of the input, and $ ask to match only at the end of the input, so if the expression match at the end and at the beggining, then both assertions are false
true - Because of the use of the Disjuntion operator (|) if either ^aa or bb$ match, then it will return true

8. What is `use strict` used for?
R:Is used to use restrictive mode, and it helps you to find errors earlier and it's also used to ban the dangerous or usless things that can launch an error on the ejececution.

9. Rewrite the following code as Ecmascript Arrow Function
```
var double = function (i) {
  return i * 2;
};
```
R: i => i * 2;

11. Explain the difference between classical inheritance and prototypal inheritance.
R: Class inheritance: Classes inherit from classes and create subclass relationships: hierarchical class taxonomies.
Prototypal Inheritance: A prototype is a working object instance. Objects inherit directly from other objects.












