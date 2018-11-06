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