# Concepts

## Js

* **Data Types:**

  * **Primitive Data Types:**
    * **String**: Represents textual data (e.g., words or sentences).
    * **Number**: Represents both whole numbers and decimal values.
    * **Boolean**: Represents two values, true or false, often used for logical conditions.
    * **Undefined**: A variable that is declared but has not been assigned a value.
    * **Null**: Represents an empty or non-existent value.
    * **Symbol**: A unique identifier, used in more advanced cases.

  * **Complex Data Types:**
    * **Object**: A collection of key-value pairs.
    * **Array**: A list-like structure that holds multiple values.
    * **Function**: A block of reusable code.

  * **Basic Control Structures:**
    * **Conditional Statements:**
      * **if statement:** Executes a block of code if a condition is true.
      * **else statement:** Executes a block of code if the condition in the if statement is false.
      * **else if:** Specifies a new condition to test, if the previous condition is false.
    * **Loops:**
      * **for loop:** Repeats code a certain number of times.
      * **while loop:** Repeats code while a condition is true.
      * **do...while loop:** Similar to a while loop, but it guarantees the loop executes at least once.

  * **Switch Statement:**
    * Another way to handle multiple conditions, often used as a cleaner alternative to multiple if...else if statements.

* **Differences between var, let and const:**
  * var: Function-scoped, hoisted, and can be reassigned.
  * let: Block-scoped, hoisted (but not initialized), and can be reassigned.
  * const: Block-scoped, hoisted (but not initialized), and cannot be reassigned after declaration.

* **Types of Operators:**
  * Arithmetic Operators: These are used for performing basic math operations.
    * Addition (+), Subtraction (-), Multiplication (*), Division (/)
    * Modulus (%): Returns the remainder of a division.
    * Increment (++), Decrement (--)

  * Assignment Operators: Used to assign values to variables.
    * Simple assignment (=): Assigns the value on the right to the variable on the left.
    * Compound assignment operators: Combine arithmetic and assignment (e.g., +=, -=, *=, /=).

  * Comparison Operators: These are used to compare two values and return a Boolean (true or false).
    * Equal to (==), Not equal to (!=)
    * Strict equal (===), Strict not equal (!==): Compares both value and type.
    * Greater than (>), Less than (<), Greater than or equal to (>=), Less than or equal to (<=)

  * Logical Operators: Used to combine or invert Boolean values or expressions.
    * AND (&&): Returns true if both conditions are true.
    * OR (||): Returns true if at least one condition is true.
    * NOT (!): Inverts the Boolean value (true becomes false, and vice versa).

  * Bitwise Operators: Operate on binary representations of numbers.
    * AND (&), OR (|), XOR (^), NOT (~), etc. These are more advanced and less commonly used for everyday tasks.

  * Ternary (Conditional) Operator: A shorthand for an if...else statement.
    * Syntax: condition ? value_if_true : value_if_false

  * Type Operators:
    * typeof: Returns the type of a variable or expression.
    * instanceof: Checks if an object is an instance of a certain class or constructor.

  * String Operators:
    * Concatenation (+): Joins two or more strings together.

* **Function Declaration, Function Expression**
  * Hoisting: Function declarations are hoisted, while function expressions are not.
  * Naming: Function declarations are always named, while function expressions can be anonymous.
  
* **Rest and spread operators:**
  * **Rest Operator (...)** Gathering multiple arguments into a single array inside a function.

    ```js
    function sum(...numbers) {
      return numbers.reduce((total, num) => total + num, 0);
    }

    console.log(sum(1, 2, 3)); // Output: 6
    console.log(sum(5, 10, 15, 20)); // Output: 50
    ``` 
  * **Spread Operator (...)** Spreading elements of an array into individual elements.
    ```js
    const numbers = [3, 4, 5];
    console.log(Math.max(...numbers)); // Output: 5
    ``` 
* **Clousures:**
  * A closure in JavaScript is a function that remembers and can access variables from its outer (or parent) scope, even after the outer function has finished executing. Closures allow inner functions to "close over" their surrounding environment and continue to reference those variables.

    ```js
    function outerFunction() {
      let counter = 0; // Variable in the outer scope

      return function innerFunction() {
        counter++; // Inner function accessing outer variable
        console.log(counter);
      };
    }

    const incrementCounter = outerFunction();
    incrementCounter(); // Output: 1
    incrementCounter(); // Output: 2
    ```        