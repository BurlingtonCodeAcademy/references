# Functions

Functions are self contained blocks of code that define an action to be taken when they are called.

# Arguments

Arguments are variables which are defined by name in the function definition and are scoped to the function instance with whatever values are passed into the function when it's called.

# Calling Functions

You call a function by its name followed by a set of parentheses. Optionally you can pass values for arguments into the parentheses.

# Anonymous Functions

Anonymous functions are functions which are defined without a variable name. They are most commonly used as callback functions since they cannot be used elsewhere in your code due to the abscence of a variable name you could use to reference them.

# Defining functions

There are three main ways of defining a function, function declarations (also called function statements), function expressions, and fat arrow functions.  There are a couple of elements shared by all forms of function definitions, those are a set of parentheses which can optionally contain expected arguments to the function, and a set of curly braces that contain the action(s) the function will take when it's called. By default a function will return `undefined` unless you specify a return value with the `return` keyword. Arguments are [scoped](#function-scope) to their function.

## Function Declarations

Function Declarations are the oldest, and most prevalent way of defining functions in JavaScript. a function declaration is marked by the `function` keyword followed by the name of the function. Function declarations hoist, which means that you can do a function decalaration anywhere in scope and use it anywhere else in that scope

```js

exampleFunction(3, 4) // => returns 7.
//This will work even though the function is defined below where it's called

function exampleFunction(argOne, argTwo) { // this function takes two arguments
  return argOne + argTwo // and returns the sum of those arguments when called
}

function noArgs() { // This function takes no arguments
  return 7 // and will return a hardcoded value of 7 when called
}

noArgs() // returns 7
noArgs(12, 3) // still returns 7

```

If no value is passed in to an argument which expects arguments then the value passed in will be `undefined`. If an argument is passed to a function that doesn't accept arguments it will still work just fine, the function just won't do anything with the arguments

## Function Expressions

Function expressions are very similar to function declarations are anonymous functions that have been assigned a variable name with the `let`, `const`, or `var` keyword and can only be used below the definition in your code.

```js

multiplyNums(3, 4) // => will throw an error and crash your program

let multiplyNums = function(numOne, numTwo) {
  return numOne * numTwo
}

multiplyNums(3, 4) // => 12

```

## Fat Arrow Functions

Fat arrow functions are also called arrow function expressions. As the name implies they behave similarly to function expressions, but they also re-bind the keyword `this` to the context in which the function is defined.

```js
divideNums = (numOne, numTwo) => {
  return numOne / numTwo
}

divideNums(4, 2) // => 2
```

# Function Scope

Function definitions have their own scope, and argument variables are only accessible inside the definition. Even if there is a variable outside the function definition with the same name as the argument variable the function still creates a *new* variable with the same name inside the function's scope, and will *not* automatically pull in the external variable

# Default Values

You can give an argument a default value by assigning the argument a value in your function definition. When no argument is passed this value will be used instead.

```js
function getNum(num=0) {
  return num
}

getNum(4) // => 4
getNum() // => 0
```

# Callback Functions

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

# Async Functions

As of ECMAScript 2016 (the official name for JavaScript is ECMAScript due to copyright issues) there are a pair of new keywords `async` and `await which you can use in your function definition to allow it to behave asynchronously. This means you can pause the execution of your program while it waits for some remote data to be fetched, or a user to input something.

```js
async function getData(url) {
  let response = await fetch(url)

  return response.text()
}
```

The above function would take a url as an argument, then it would waut until it fetched all the data from the given url and only after that request has been resolved would it return the response as plain text.