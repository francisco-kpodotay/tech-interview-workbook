# Concepts

## Js

### Data Types:

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

### Differences between var, let and const:
  * var: Function-scoped, hoisted, and can be reassigned.
  * let: Block-scoped, hoisted (but not initialized), and can be reassigned.
  * const: Block-scoped, hoisted (but not initialized), and cannot be reassigned after declaration.

### Types of Operators:
  * Arithmetic Operators: These are used for performing basic math operations.
    * Addition (```+```), Subtraction (```-```), Multiplication (```*```), Division (```/```)
    * Modulus (```%```): Returns the remainder of a division.
    * Increment (```++```), Decrement (```--```)

  * Assignment Operators: Used to assign values to variables.
    * Simple assignment (=): Assigns the value on the right to the variable on the left.
    * Compound assignment operators: Combine arithmetic and assignment (e.g., ```+=```, ```-=```, ```*=```, ```/=```).

  * Comparison Operators: These are used to compare two values and return a Boolean (true or false).
    * Equal to (```==```), Not equal to (```!=```)
    * Strict equal (```===```), Strict not equal (```!==```): Compares both value and type.
    * Greater than (```>```), Less than (```<```), Greater than or equal to (```>=```), Less than or equal to (```<=```)

  * Logical Operators: Used to combine or invert Boolean values or expressions.
    * AND (```&&```): Returns true if both conditions are true.
    * OR (```||```): Returns true if at least one condition is true.
    * NOT (```!```): Inverts the Boolean value (true becomes false, and vice versa).

  * Bitwise Operators: Operate on binary representations of numbers.
    * AND (```&```), OR (```|```), XOR (```^```), NOT (```~```), etc. These are more advanced and less commonly used for everyday tasks.

  * Ternary (Conditional) Operator: A shorthand for an if...else statement.
    * Syntax: condition ```?``` value_if_true ```:``` value_if_false

  * Type Operators:
    * typeof: Returns the type of a variable or expression.
    * instanceof: Checks if an object is an instance of a certain class or constructor.

  * String Operators:
    * Concatenation (```+```): Joins two or more strings together.

### Function Declaration, Function Expression
  * Hoisting: Function declarations are hoisted, while function expressions are not.
  * Naming: Function declarations are always named, while function expressions can be anonymous.
  
### Rest and spread operators:
  * **Rest Operator (```...```)** Gathering multiple arguments into a single array inside a function.

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
### **Clousures:**
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

### Optional Chaining (```?.```)
  Optional chaining allows you to safely access deeply nested properties of an object without having to check if each reference in the chain is valid (not null or undefined).
  
### Mutable and immutable data structures
  * **Mutable** data structures are those whose contents can be changed or modified after creation. You can add, update, or delete elements within these data structures without creating a new instance. The data structure itself remains the same in memory, but its contents can change. 

  * **Immutable** data structures are those whose contents cannot be changed after they are created. Any modification to an immutable data structure results in the creation of a new data structure with the modified content, while the original remains unchanged.

### Promises and the async/await
  * A **promise** is an object representing the eventual completion or failure of an asynchronous operation. It can be in one of three states:

    * **Pending**: The initial state, neither fulfilled nor rejected.
    * **Fulfilled**: The operation was successful, and the promise is resolved with a result.
    * **Rejected**: The operation failed, and the promise is rejected with an error.

  * **Async/await** is built on top of promises, providing a more readable and cleaner syntax for handling asynchronous code. With async/await, you can write asynchronous code that looks more like synchronous code.
    * **async** function: Declares a function that returns a promise. Any value returned from the function is implicitly wrapped in a resolved promise.
    * **await**: Pauses the execution of the async function and waits for the promise to resolve (or reject). The function resumes execution after the promise resolves.

### Classes

  * **Classes** are blueprints for creating objects.
  * **Constructor** initializes the object’s properties (fields) when it is instantiated.
  * **Methods** define the behavior of the objects (instance or static methods).
  * **Fields (Properties)** store the data associated with the object, which methods can manipulate.

  * **Class Inheritance (extends):** Reuses functionality from a parent class and allows for method/property overriding.
  * **Private Properties:** Use the # symbol to protect class data, ensuring it is only accessible inside the class.
  * **Static Methods/Properties:** Class-level methods and properties that can be accessed without creating an instance of the class.

### Access Modifiers


  * In **JavaScript**, access modifiers are not explicitly defined like in some other languages, but similar functionality can be achieved:

    * **Public:** Default in JavaScript. Members are accessible from anywhere (inside and outside the class).

    * **Private:** Achieved using the # syntax. Members are only accessible within the class itself and cannot be accessed from outside or in subclasses.
    * **Protected:** Not natively supported in JavaScript. This can be simulated using naming conventions (e.g., prefixing properties with an underscore _), suggesting that these properties should not be accessed outside the class, but this is not enforced.

  * **TypeScript** provides explicit access modifiers that enhance the control over member visibility:

    * **Public:** Accessible from anywhere (inside, outside the class, and in subclasses). Default if no access modifier is specified. Used when properties or methods should be freely accessible.

    * **Private:** Accessible only within the class where declared. Not accessible in subclasses or outside the class. Used to hide implementation details or sensitive data. Enforced at compile-time for better type safety.
    * **Protected:** Accessible within the class and its subclasses, but not from outside the class hierarchy. This allows controlled access for inherited classes.
    * **Readonly:** This modifier can be applied to properties to indicate that they cannot be modified after their initial assignment. In TypeScript, this means the property is read-only and can only be set within the constructor or during declaration.

  * **Key Differences**
    * Explicit Access Modifiers: TypeScript has defined keywords (public, private, protected, readonly) for access control, while JavaScript uses conventions and syntax (like #) for private members without formal enforcement.

    * Compile-time Enforcement: TypeScript enforces access modifiers at compile time, providing type safety, whereas JavaScript relies on runtime behavior.
    * Protected Members: TypeScript explicitly supports protected, while JavaScript does not have a native equivalent, relying instead on naming conventions.
    * Readonly Modifier: TypeScript allows properties to be marked as readonly, preventing modification after initial assignment, while JavaScript does not have a direct equivalent to enforce immutability on properties.

### Object Prototypes
  * **Object Prototypes** are a fundamental feature of JavaScript that enables inheritance and the sharing of properties and methods between objects. Understanding prototypes is essential for leveraging JavaScript's prototypal inheritance model. Here’s a breakdown of key concepts related to object prototypes:

    * In JavaScript, every object has a property called ```[[Prototype]]```, which is a reference to another object. This reference is what allows objects to inherit properties and methods from other objects.
    * The prototype object can be used to define shared properties and methods that multiple objects can access, reducing memory usage and promoting code reuse.
  
* Using Object Literals
  ```js
  const animal = {
    sound: 'generic sound',
    makeSound() {
      console.log(this.sound);
    }
  };

  const dog = Object.create(animal);
  dog.sound = 'bark';
  dog.makeSound(); // Output: bark

  ```
* Using Constructor Functions
  ```js
  function Animal(sound) {
    this.sound = sound;
  }

  Animal.prototype.makeSound = function() {
    console.log(this.sound);
  };

  const cat = new Animal('meow');
  cat.makeSound(); // Output: meow
  ```
* Setting Prototypes with Object.create()
  ```js
  const parent = {
    greet(name) {
      console.log(`Hello, ${name} from parent`);
    }
  };

  const child = Object.create(parent);

  // Calling the greet method with a parameter
  child.greet('Alice'); // Output: Hello, Alice from parent
  ```