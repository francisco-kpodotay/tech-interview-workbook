# Programming Basics questions

## Data basics

What are the differences between objects and arrays? What is the purpose of the object and what is the purpose of the array?
  - Object is an unordered collection of key-value pairs
  - Array is a list of elements.

How can you access a key's value in an object?
  - Object.keyname will point to the value of the key.

How can you access the first and the last item of an array?
  - arrayName[0], arrayName[array.length - 1]

Name all the primitive types in JavaScript.
  - bigint, symbol, null, undefined, string, number, boolean,

## Algorithm basics

What are the assignment operators? Name some of them.
  - They assign(hozzárendelni) value(s) to variables.
      =, +=, -=, *=

What are the arithmetic operators? Name some of them.
  - modify a number
      +, -, *, /

What are the comparison operators? Name some of them.
  - They compare two values or expressions with each other.
      ==, !=, ===, !==, <, >, <=, >=

What are the logical operators? Name some of them.
  - They execute logical operations on boolean values.
      && (And), || (Or), ! (Not, Negal),

What is the difference between `for`, `for of` and `for in`?
  - "for" loop is a standard loop 
    - Initializer: Initialize a counter variable to start with
    - Condition: specify a condition that must evaluate to true for next iteration
    - Iteration: increase or decrease counter
  - "for..of" loops through all the items one by one.
  - "for..in" loops through the keys of an Object

How do you find the average of values in an array if you can’t use any built-in functions or methods?
  - array of numbers: sum all the numbers using a loop, then divide the sum with array.length

## Function basics

What are the main parts of a function?
  -Name, parameters, body.

What is the difference between parameters and arguments?
  - parameter is when you declare a function, argument when you invoke a function

What are the differences between function expression and function statement?
  - Function expressons are assigned to a variable with an anonim function as a value
        const minusOne = function (num){return num - 1}
  - Function declarations uses the function keyword and a name of the function 
        function minusOne(num){return num - 1}
  - You can call both the same way

## OOP Basics

What is a method?
  - methods are functions inside Objects

Name 3 builtin functions (and/or methods) regarding strings.
  - .slice(), .indexOf, includes()

Name 3 builtin functions (and/or methods) regarding arrays.
  - .slice(), .indexOf, includes()

Name 3 builtin functions (and/or methods) regarding numbers.
  - Math.floor(), Math.random(), Math.sqrt()

## FP Basics

What is a callback function?
  - A function passed into another function as an argument.

What are the differences between `for` loops and `forEach`?
  - for loop just iterates over, forEach calls a function over each element

## File basics

What is the difference between JavaScript data structures and JSON data structures?
  - JavaScript data structures are used for in-memory data manipulation within JavaScript code and can be more complex, while JSON data structures are a simple text-based format primarily used for data interchange between systems and have a restricted set of data types.

How do you create JavaScript data structure from a JSON file's data?
  - With the the built in JSON.parse() method.

## View Basics

What is the difference between JavaScript data structures and DOM (HTML document) data structures?
  - javascript data structures are used for computation with javascript code
  - the DOM represents the structure of a HTML page in a tree like structure

What are the steps of changing a HTML element's content with JavaScript?
  - Grab the element (getElementById), modify content using element.innerHTML('html code here').
  - JPG1

## Event basics

What is an event listener?
  - An event listener is a javascript function that waits for a specific event, and then executes the specified code (callback fn).

What are the steps of changing a HTML element's content when the element clicked?
  - we need to grab the element, put an eventlistener on it, change the innerHTML or innerText 

Inside a `click` event listener, how can you access the element that has been clicked?
  - With the call back function you can pass a parameter and that parameter's target key you can directly access and modify that element
  - addEventListener('click', (event) => {
    console.log(event.target.id)
    })

## Design Basics

What are the differences between `display: block` and `display: inline` CSS properties?
  - block elemnts:
    - take up all the parent element's width
    - have a "linebreak" at there ends
    - can set the height and width of the element
  - inline element:
    - only taking up that many space as necessarry
    - don't have any linebreak
    - can't set a width and height

What are the differences between `position: relative` and `position: absolute` CSS properties?
  - position: relative
    - relatively to it's normal position
  - position: absolute
    - rely on there parent or sibling element
    - takes the element out of the normal document flow

What is the box model, name the CSS properties connecting to it?
  - Box model is a design layout term, and is essentially a box that wraps around every html element. It consists of:
    - Margin, border, padding, content.
 
What CSS properties affect font and text appearance?
    - font
        - font-style
        - font-variant 
        - font-size
        - font-weight 
        - font-family
    - text-align
    - line-height
    - letter-spacing and word-spacing
    - text-decoration, text-transform, and text-shadow
    - color

What are the steps of adding or removing a HTML element's class name?
  - we need to grab the html element, then classList.remove('thatclass')

## JavaScript - language specialties

What is the difference between value and reference data types in terms of object and primitives?
  - Primitive values are immutable, we can point to them but can't change them. Reference data types (obj, array) are mutable. Copying an array to a different variabla and changing it there modifies the original array as well.

Is `null` an object or a primitive?
  - null is a primitive

What is `undefined`?
  - undefined is a primitive

When to use `var`, `let`, and `const`?
  - var is not recommended anymore
  - let when we want to REASSGN the value later
  - const is constant and CANNOT BE REASSIGNED (value of the variable wont change later)

What is hoisting?
  - Hoisting is JavaScript's default behavior of moving declarations to the top.

## Git

What are the advantages of using a version control system?
  - Managing and protecting the source code
  - Keeping track of all the modifications of the code
  - Comparing earlier versions of the code
  - ???Collaboration: allow multiple developers to work on the same codebase

What’s the difference between Git and GitHub?
  - Git is the version control system itself, gitHub is a cloud based hosting service to store git repos.

What are remote repositories in Git?
  - a git repo that is hosted on the internet 

Why does a merge conflict occur? (Miért fordul elő összevonási konfliktus?)
  - When two developer modify the same lines of code and git can't decide which ones to keep.

## Terminal

How do you run a JavaScript file in the terminal?
  - open up terminal, node command javascript file location

How do you stop a running a command in the terminal?
  - "Ctrl + c"

How go you get the previous command in the terminal?
  - "Up Arrow"

How do you got to the current directory's parent directory in the terminal?
  - cd .. 
 