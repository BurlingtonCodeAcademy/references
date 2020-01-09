# Glossary of Terms

## Arrays

An ordered collection of things. Arrays can contain any type type of value, including other arrays, and are defined using square brackets: `[]`.

```javascript
let array = ['string', 1234, variableName, {name: 'object'}, ['banana', 'apple']]
```

## Bang

"**!**", the not operator, also called an exclamation point. Inverts the truthiness of a statement

```javascript
!true // => false
```

## Block

A chunk of code contained within curly braces, {}. Blocks have a local scope.

```javascript
{
  let string = "this is block scope"

  string // => "this is block scope"
}

string // => undefined
```

## Callback Function

A function which is passed to another function as an argument.

```javascript
function callContainer(callback) {
  callback() // accepts a function as an argument then calls that function
}

function sayHello() {
  console.log("Hello")
}

callContainer(sayHello) // sayHello is being used as a callback function
```

Note that the function that's being passed in as a callback is NOT being called when it is passed in. It's the responsibility of the container function to call the callback

## Class

A class is essentially an object template, or prototype. They are defined with the `class` keyword and a are almost always given a capitalized name.

  ### Constructor

  A constructor is a special function on classes that allows you to predefine the properties on the objects of that class.

```javascript
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width
    this.area = this.area.bind(this)
  }

  area() {
    return this.height * this.width
  }
}
```

## DOM

The Document Object Model is an object that represents an HTML page that tells the browser what to display. The DOM can be manipulated without changing the HTML source code as it is unique to each instance of the HTML being run in the browser.

## Event Handler

A function that waits for some event and then triggers a callback function once that event is triggered

```javascript
element.addEventListener('event', callbackFunction)

setInterval(1000, callbackFunction)
```

## Function

A self contained block of code. Functions are defined with the `function` keyword, optionally a name for the function, an open and close parentheses, which may have argument variables, and an open and closed set of curly braces defining the body of the function where the action of the function happens. Functions can also be written in 'fat arrow' syntax in which case they don't need the function keyword, and instead have a fat arrow `=>` between the parentheses, and the curly braces.
>Functions return `undefined` unless they have a specific value returned, marked by the `return` keyword

```javascript
function add(arg1, arg2) { // classic fuction definition
  return arg1 + arg2
}

fatArrowFunction = (arg) => {
  console.log(arg)
}

let anotherValidFunction = function() {
  console.log('You can only call me below this definition')
}
```

Functions set to a variable name with the `let`, `const`, or `var` keyword do not hoist and can only be used after being defined.

## HTML

Hyper Text Markup Language. It's a high level programming language, and the face of the World Wide Web.

## Instance

A specific usage of a value, each instance is unique (even if they have the same result).

```javascript
function doSomething(thing) {
  //does stuff
}

doSomething(valueOne)//an instance of the function doSomething
doSomething(valueTwo)//a different instance of doSomething 
```

## I/O

Input/Output, The parts of the computer you interact with.  Input is anything that allows energy or information to enter the system i.e. the keyboard, or the console. Output is anywhere that displays information from the system i.e. the screen, or the console.
>Sometimes things can act as both input and output such as the terminal, or a touch screen which you can not only accept input with, but also displays information, 

## Iterator

A method that loops over the properties of an object or an array, and performs an action on them. Common iterators are the `forEach` method on arrays, `for ... of` loops, and `for ... in` loops.

```javascript
let array = ['a thing', 'another thing']
array.forEach(thing => console.log(thing))

for (thing of array) {
  console.log(thing)
}

for (index in array) {
  console.log(array[index])
}
```

## Library

A library is a plugin for a programming language that exteneds or changes the way that language behaves. i.e. Express is a JavaScript Library that makes server-side programming in JavaScript easier.

## Method

A method is a function attached to an [object](#object). If you define a method using fat arrow syntax it will bind the keyword `this` to the object the method is attached to.

```javascript
const object = {
  method() {
    console.log("I'm a method!")
  }

  anotherMethod = () => {
    console.log("I'm a fat arrow method!")
  }
}
```

## Null

Null values that in for "nothing" and always evaluate as `false` when using evaluating the [truthiness](#truthiness) of a statement. Javascript has several nulls:

  * `null` Nothing, there is no value
  * `undefined` I don't know what the value is
  * `NaN` Not a Number
  * `''` Empty String
  * `0` The number zero
  * `false` The boolean value that's not true

## Object

An object is a collection of key value pairs. The values can be any JavaScript value, including functions (in which case they are called methods), and the keys are strings. Objects are created using curly braces to deliniate the object with the keys and their values seperated by colons, and the key/value pairs seperated by commas

```javascript
let object = {
  name : "Leeloo Dallas",
  "multi pass": true,
  number: 2,
  thisIsAMethod() {
    if(this["multi pass"]) {
      return "access granted"
    }
    else {
      return "access denined"
    }
  },
  inception: {
    aProperty: "objects in objects"
    }
}
```

## Operator

A value that sends a message to the value to its left.

```js
  3 + 4 // => 7
```

The plus operator in the above example reads in the values to its left (3) and right (4), adds the value from its right to the value on its left and returns a new value (7)

## Queue

An ordered collection that is "first in, first out." There is no Queue object in JavaScript, but we can use [arrays](#arrays) like queues with the `push` and `shift` methods.

## Recursion

When you call a function inside of itself to cause a loop

```javascript
function count(num){//function that takes a number
  console.log(num)// prints the number
  count(num + 1)// and recurses to count infinitely(or at least until it exceeds the callstack and errors out)
}
```

## Refactor

ReWriting already functional code, and making it cleaner without changing its functionality.

## Regular Expression

A low level programming language most often used for string matching.

## Scope

The context of your code. Used to determine which variables are accessable by what code.

## Stack

An ordered collection that is "first in, last out." There is no Stack object in JavaScript, but we can use [arrays](#arrays) like stacks with the `push` and `pop` methods.

## Terminal

An aplication on your computer that acts as a text based interafce for directly manipulating operations on your computer.

  #### Command Line

  The section of the terminal you type into, marked with some sort of prompt, usually a `>` or `$`

## Truthiness

The Truthiness of an expression is whether it evaluates as `true` or `false`. Most expressions will evaluate true unless they return a [null value](#null).

## this

`this` is a special keyword that points to the containing scope of a method definition in an object, or to the function it's contained within. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

## Type

A specific type of value, i.e. `number`, or `string`

## Variable

Something that stands in for something else, and is bound to the scope in which it's defined. Declared with the `let`, `const`, or `var` keyword. `let` allows a variable to be mutated. `const` does not allow the variable to be mutated. `var` is older and behaves a lot like let, but doesn't allways bind to it's containing scope, and **should never be used**, but you will see it all over the place so it's important to recognize it.
