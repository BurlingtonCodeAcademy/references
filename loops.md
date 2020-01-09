# Loops

Loops are very useful. They allow you to reapeat a certain chunk of code over and over until a given conditon is met. Loops generally consist of  keyword that defines the type of loop, a condition inside parentheses which acts as a truth check, and the code to be executed inside a set of curly braces immediately following the parentheses that contain the truth check. A loop will execute the code inside its body (the content of the curly braces) until the truth check evaluates `false`. Beware infinite loops, if the truth check always evaluates true it will lock your program in an infinite loop.

# `while` Loops

`while` loops are the most common, and probably simplest type of loop in JavaScript. They read "while some condition is true, execute this code"

```js
let num = 10
while(num > 0) {
  console.log(num)

  num = num - 1
}
```

The above code first defines a varaible outside the loop to check against. Then the loop checks if `num` is greater than 0 if it is the program prints the value of `num` to the console, and then decreases the value of `num` by one.  This program will print 10 9 8 7 6 5 4 3 2 1 and then exit since on the final run `num` equals 0 so it is not greater than 0 and the loop exits.

# `for` Loops

`for` loops are the oldest form of loop in JavaScript, and are a bit more condensed than `while` loops. The look similar except the keyword they use is `for` instead of `while` and the have the variable to check against, the target value, and the action to be taken on the variable each loop all in the initial parentheses.

```js
for(let num = 10; num > 0; num = num - 1) {
  console.log(num)
}
```

The above `for` loop behaves exactly the same as the preceding `while` loop.
