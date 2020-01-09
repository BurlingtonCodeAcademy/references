# Methods on Strings

Methods do NOT mutate the strings they're called on. They return NEW strings with the return value of the method. So if you want to access the return value of the method elsewhere in your code you will need to set it to a variable.

## .charAt(num)

Returns the character to the right of the specified index

```javascript

'dog'.charAt(1) // => 'o'

```

## .slice(num1, num2)

Returns a string from the right of the first specified index to the left of the second specified index, or the end of the string if no second argument is passed.

```javascript

'supercalifragilisticexpialadocious'.slice(5, 9) // => 'cali'

'supercalifragilisticexpialadocious'.slice(9) // => 'fragilisticexpialadocious'

```

## .toLowerCase()

returns a lowercase version of the string it's called on.

```javascript

'HeLlo'.toLowerCase() // => 'hello'

```

## .toUpperCase()

returns a capitalized version of the string it's called on.

```javascript

'hello'.toUpperCase() // => HELLO

```


## .split(char)

returns an array of strings split at the specified character.

```javascript

'blueberry'.split('e') // => ['blu', 'b', 'rry']

```
# Methods on Numbers

Numbers also have some methods that can be called on them.  There is also a globally available `Math` class available in JavaScript which has a number of useful methods attached to it.

## .toString()

takes a number object and turns it into a string

```javascript

let x = 10
x.toString() // => '10'

(42).toString() // => '42'

```

>Note that you will need to assign the value of the number to a variable (or wrap it in parentheses) and then call `.toString()` on it otherwise you'll get `SyntaxError: Invalid or unexpected token`.

## .toPrecision(num)

takes a number object and evaluatues it to a specified number of places

```javascript

(7.54321768).toPrecision(4) // => 7.543

```

## Math.floor(num)

trims all decimal places off a given number

```javascript

Math.floor(134.97837) // => 134

```

>Note that this does not round the number, it just trims off everything after the decimal 

## Math.round(num)

rounds a given number to the nearest integer

```js
Math.floor(5.9) // => 6
Math.floor(5.4) // => 5
```

## Math.random()

returns a random number between 0 (inclusive) and one (exclusive)

```javascript

Math.random() // => a random number between 0 and 0.99999999999...

```
