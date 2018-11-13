# Intro to JavaScript

## Week 1

### Topics
This week's session will cover the following concepts:
 - Types in JavaScript
 - Variables
 - JavaScript Operators
 - Loops
 - Conditional Execution
 - Functions

### Setting Up
JavaScript is really easy to get working. Just download this repository, open the folder and navigate to `Week 1/resources` and open `index.html` in you browser of choice. We recommend you use Google Chrome or Mozzila Firefox.

That's it! JavaScript runs in the browser, so getting started is super easy.

### Types
JavaScript has six primitive data types. These are types that just about everything is made up of.

The primitive types are:
 - Boolean
 - Null
 - Undefined
 - Number
 - String
 - Symbol

You'll note that only three of the types realy seem like data types, `Boolean`, `Number`, and `String`. And you'd be correct with that assumption, in the sense that you'll rarely define variables with the other types.

`Null` and `Undefined` serve similar purposes, that being to fill nothing. However, the core diference is `Undefined` is more likely to cause an error than `Null`. Undefined is usually made when you attempt to call a function or variable that doesn't exist. Wheras null will usually be used when you'll set something later.

`Symbol` is a new primitive type, that we won't be using in this series.

There is also another type, that being an `Object`. Which many of the other JavaScript data types are made of. We'll go into more detail on objects in Week 3.

## Variables
Variables are the core of JavaScript. Everything is a variable, i.e. everything is callable.

Creating a variable is very simple, you just intialize it with the keyword `var`, `let`, or `const`.

`var` and `let` are functionally identical. The only difference is that `var` creates a variable in global scope, whereas, `let` is local or block scope. 

`const` is also restricted to local scope, but it's values cannot be modified*

```JavaScript
const myConst = "You can't change this"
let myLet = "This is a local variable"
var myVar = "this is a globalVariable"
```

###### * sort of

### Operators

JavasScript, like most other languages, has several main operators. Those being:
 - `!` not
 - `&&` and
 - `||` or
 - `==` equals
 - `!=` not equals
 - `===` equals (same type)
 - `!==` no equals (same type)
 - `<` Less than
 - `>` Greater than
 - `<=` Less than or equal to
 - `>=` Greater than or equal to

### Loops
There are two (or three) types of loops in JavaScript.

#### While Loop
The first an most basic kind of loop is a while loop.

While loops will carry out the sam set of instructions until a certain condition is met.

```JavaScript
let done = false;
while (!done) {
  // do something
}
```

The above example will do whatever you've put between the curly braces `{ }` until `done == true`. The code block doesn't specify what to do, however, you could set it so that if something is happening, set `done` to `true`.

#### For Loop
For loops are very similar to a while loop, in the sense that they have a condition, but they also execute code in every iteration, regardless of the block content.

The syntax for a for loop is as follows:

`for (<variable>; <condition>; <execute>) { }`

An example fo a for loop would be the following:
```JavaScript
for (let i = 0; i < 100; i++) {
  // do something
}
```

the above example will execute a given instruction 100 times. This is because:
1. When initialising the loop, we sent a cosntant of `i` to equal `0`.
2. The loop will continue to execute until `i` is less than `100`.
3. We increment `i` by `i` after every execution.


You'll also not that we could write the above for loop using a while loop. It would look like the following:
```JavaScript
let i = 0;
while (i < 100) {
  // do something
  i++;
}
```

As you can see, instead of defining the `i = 0` and the `i++` in the loop definition, we've set them outside and inside the loop, respectively.

#### For...of Loop
There is one final type of loop. A for...of loop. In order to understand what a for...of loop is you must first understand arrays.

##### Arrays
Arrays are set a values store under one variable. An array could be a set of strings, a set of numbers, or even a set of arrays. Arrays are of type object.

Here are a few example arrays:
```JavaScript
const years = [2000, 2001, 2002, 2003, 2004];
const students = ["Alice", "Bob", "Carol", "Dave"];
```

In order to access an element in array we have to use it's index. The first element in an array will have an index of `0`.

```JavaScript
years[0] // 2000
years[3] // 2003
students[3] // Dave
students[4] // undefined
```

##### The loop
For...of loops allow us to iterate over an array, and do something with each element.

Traditionally we would've had to use a for loop that looked something like this to iterate over an array:
```JavaScript
for (var i = 0; i < students.length; i++) {
  var student = students[i];
  // do something with student
}
```

In modern JavaScriot, arrays, because they are an object, have a special functions that are technically symbols (i.e. they're hidden) called an iterator function that allow you to access the next element in an array.

A for...of loop would look something like this
```JavaScript
for (const student of students) {
  // do something with student
}
```

This does the exact same thing as the previous for loop, just in less code.

You'll also note that I used a `const` instead of a `let` or `var`. This is becaue, in a for...of loop, the element variable is redefined, not changed, unlike in a for loop.

#### `continue` and `break`
When working with loops, there are two keywords we can use to manipulate how the loop works, regardless of wether or no the condition has been met.

They are `continue` and `break`.

##### continue
Continue will halt execusion and move on to the next iteration of the loop. This is useful when a certain requirment has been satisfied and you no longer need to keep maniuplating a particular subset of the data.

```JavaScript
while (true) {
  // do something
  continue; // execution stops ehre and start again
  // do some more
}
```

##### break
Break does the same thing as continue, except that instead of starting loop execution again, it halts execution and will execute code after the loop.

```JavaScript
while (true) {
  // do something
  break; // loop no longer executes
}
```

### Conditional Expressions
Conditional execution is when you only execute a block of code if a specific condition is met. Similar to how loops work.

There are two ways to execute conditionall in JavaScript. If statements, and switch...case blocks.

#### If Statements
If statements are the way you'll typically execute conditionally in JavaScript. 

They look like the following:
```JavaScript
const myConst = 1;
if (myConst == 1) {
  // do one thing
} else if (myConst == 2) {
  // do another thing
} else {
  // didn't match any of the if statements, so do this.
}
```

#### Switch...case blocks
switch...case  are very convenient when you need to execute code only based on one parameter that will usually have one of a specific set of values.

They work by passing a value to each of the conditional case blocks.

Example as follows:
```JavaScript
const myConst = 4;
switch (myConst) {
  case 1:
    // do one thing
    break;

  case 2:
    // do another thing
    break;

  case 3:
    // do a third thing
    break;

  case 4:
    // do a fourth thing
    break;
  
  default:
    // do this if myConst wasn't 1, 2, 3, or 4
    break;
}
```

You'll not the used of `break` statements. These are used because a swtich block will execute the code for each case that meaches.

### Functions
Functions allow you to assign a variable to a specific code block to be executed later.

There are two ways to create function. You can either assign a variable to a function by using "fat arrow" syntax. Or you can use the function keyword. Here are two examples.

```JavaScript
const fatArrowFunction = () => {
  // this is a function
}

function myFunction() {
  // this is also a function
}

// executing the functions
fatArrowFunction();
myFunction();
```

You can also create parameters that can be accessed locally within the function. We also use a return keyword to pass a value out of the function.

```JavaScript
const myFunction = (myVar) => {
  return myVar + 1;
}

const myResult = myFunction(3);
// myResult = 4
```
