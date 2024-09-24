# TypeScript Workbook Basic

## Table of Contents

1. [Basic Types](#basic-types)
2. [Interfaces](#interfaces)
3. [Classes](#classes)
4. [Functions](#functions)
5. [Generics](#generics)
6. [Modules](#modules)
7. [Advanced Types](#advanced-types)
8. [Decorators](#decorators)
9. [TypeScript with React](#typescript-with-react)
10. [Q&A](#typescript-workbook-qa)

--- 

## Basic Types

```typescript
// Basic Types
let isDone: boolean = false;
let decimal: number = 6;
let color: string = "blue";

// Arrays
let list: number[] = [1, 2, 3];

// Tuples
let x: [string, number];
x = ["hello", 10];

// Enums
enum Color {
  Red,
  Green,
  Blue
}
let c: Color = Color.Green;

// Type Assertions
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

## Interfaces
```typescript
// Defining an Interface
interface User {
  name: string;
  age: number;
  isAdmin?: boolean; // optional property
}

// Using Interfaces
function greet(user: User) {
  return `Hello, ${user.name}`;
}

// Extending Interfaces
interface Admin extends User {
  adminLevel: number;
}
```

## Classes
```typescript
// Defining a Class
class Animal {
  name: string;
  constructor(name: string) {
    this.name = name;
  }
  move(distance: number = 0) {
    console.log(`${this.name} moved ${distance}m.`);
  }
}

// Inheritance
class Dog extends Animal {
  bark() {
    console.log("Woof! Woof!");
  }
}

// Access Modifiers
class Cat extends Animal {
  private sound: string = "Meow";

  makeSound() {
    console.log(this.sound);
  }
}
```

## Functions
```typescript
// Function Types
function add(x: number, y: number): number {
  return x + y;
}

// Optional and Default Parameters
function buildName(firstName: string, lastName = "Smith"): string {
  return firstName + " " + lastName;
}

// Rest Parameters
function sum(...numbers: number[]): number {
  return numbers.reduce((a, b) => a + b, 0);
}
```

## Generics
```typescript
// Basic Example
function identity<T>(arg: T): T {
  return arg;
}

// Generic Classes
class GenericNumber<T> {
  zeroValue: T;
  add: (x: T, y: T) => T;
}
```

## Modules
```typescript
// module1.ts
export const PI = 3.14;
export function calculateCircumference(diameter: number): number {
  return diameter * PI;
}

// module2.ts
import { calculateCircumference } from "./module1";
console.log(calculateCircumference(7));

```

## Advanced Types
```typescript
// Union and Intersection Types
function combine(input1: number | string, input2: number | string) {
  if (typeof input1 === "string" || typeof input2 === "string") {
    return input1.toString() + input2.toString();
  }
  return input1 + input2;
}

// Type Guards
function isNumber(x: any): x is number {
  return typeof x === "number";
}

// Type Aliases
type Name = string;
type NameOrAge = Name | number;

```

## Decorators
```typescript
// Basic Decorator
function sealed(constructor: Function) {
  Object.seal(constructor);
  Object.seal(constructor.prototype);
}

// Class Decorators
@sealed
class BugReport {
  type = "report";
  title: string;
  constructor(t: string) {
    this.title = t;
  }
}
```

## TypeScript with React
```typescript
// Installing Dependencies
// npx create-react-app my-app --template typescript

// Functional Components with TypeScript
import React from 'react';

interface GreetingProps {
  name: string;
}

const Greeting: React.FC<GreetingProps> = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};

export default Greeting;
```

# TypeScript Workbook Q&A

## Table of Contents

1. [What is TypeScript?](#q1-what-is-typescript)
2. [How do you define a variable in TypeScript?](#q2-how-do-you-define-a-variable-in-typescript)
3. [What are the basic types in TypeScript?](#q3-what-are-the-basic-types-in-typescript)
4. [What is the difference between `any` and `unknown`?](#q4-what-is-the-difference-between-any-and-unknown)
5. [How do you define an interface in TypeScript?](#q5-how-do-you-define-an-interface-in-typescript)
6. [What is the purpose of optional properties in interfaces?](#q6-what-is-the-purpose-of-optional-properties-in-interfaces)
7. [How do you create a class in TypeScript?](#q7-how-do-you-create-a-class-in-typescript)
8. [What are access modifiers in TypeScript?](#q8-what-are-access-modifiers-in-typescript)
9. [How do you implement inheritance in TypeScript?](#q9-how-do-you-implement-inheritance-in-typescript)
10. [What is a union type in TypeScript?](#q10-what-is-a-union-type-in-typescript)
11. [What is an intersection type in TypeScript?](#q11-what-is-an-intersection-type-in-typescript)
12. [How do you create and use generics in TypeScript?](#q12-how-do-you-create-and-use-generics-in-typescript)
13. [What is a tuple in TypeScript?](#q13-what-is-a-tuple-in-typescript)
14. [How does TypeScript handle enums?](#q14-how-does-typescript-handle-enums)
15. [What is type assertion in TypeScript?](#q15-what-is-type-assertion-in-typescript)
16. [How do you define a function in TypeScript?](#q16-how-do-you-define-a-function-in-typescript)
17. [What are the differences between interfaces and type aliases?](#q17-what-are-the-differences-between-interfaces-and-type-aliases)
18. [How do you handle null and undefined in TypeScript?](#q18-how-do-you-handle-null-and-undefined-in-typescript)
19. [What are decorators in TypeScript?](#q19-what-are-decorators-in-typescript)
20. [How do you use TypeScript with React?](#q20-how-do-you-use-typescript-with-react)
21. [What are modules in TypeScript?](#q21-what-are-modules-in-typescript)
22. [How do you export and import modules in TypeScript?](#q22-how-do-you-export-and-import-modules-in-typescript)
23. [What are namespaces in TypeScript?](#q23-what-are-namespaces-in-typescript)
24. [How do you use async/await in TypeScript?](#q24-how-do-you-use-async-await-in-typescript)
25. [What are ambient declarations in TypeScript?](#q25-what-are-ambient-declarations-in-typescript)
26. [How does TypeScript support JSX?](#q26-how-does-typescript-support-jsx)
27. [What are the advantages of using TypeScript over JavaScript?](#q27-what-are-the-advantages-of-using-typescript-over-javascript)
28. [How do you handle errors in TypeScript?](#q28-how-do-you-handle-errors-in-typescript)
29. [What is the difference between `let`, `var`, and `const` in TypeScript?](#q29-what-is-the-difference-between-let-var-and-const-in-typescript)
30. [How do you configure the TypeScript compiler with `tsconfig.json`?](#q30-how-do-you-configure-the-typescript-compiler-with-tsconfigjson)
31. [What is the `void` type in TypeScript?](#q31-what-is-the-void-type-in-typescript)
32. [How do you create a readonly property in TypeScript?](#q32-how-do-you-create-a-readonly-property-in-typescript)
33. [What is a `never` type in TypeScript?](#q33-what-is-a-never-type-in-typescript)
34. [How do you use TypeScript with existing JavaScript libraries?](#q34-how-do-you-use-typescript-with-existing-javascript-libraries)
35. [What is a type guard in TypeScript?](#q35-what-is-a-type-guard-in-typescript)
36. [How do you create a custom type guard in TypeScript?](#q36-how-do-you-create-a-custom-type-guard-in-typescript)
37. [What is the `keyof` operator in TypeScript?](#q37-what-is-the-keyof-operator-in-typescript)
38. [How do you define a mapped type in TypeScript?](#q38-how-do-you-define-a-mapped-type-in-typescript)
39. [What is `type inference` in TypeScript?](#q39-what-is-type-inference-in-typescript)
40. [What are conditional types in TypeScript?](#q40-what-are-conditional-types-in-typescript)
41. [How do you use `infer` in conditional types?](#q41-how-do-you-use-infer-in-conditional-types)
42. [What is the purpose of `this` type in TypeScript?](#q42-what-is-the-purpose-of-this-type-in-typescript)
43. [How do you use type intersections to merge types?](#q43-how-do-you-use-type-intersections-to-merge-types)
44. [What is the `ReadonlyArray` type in TypeScript?](#q44-what-is-the-readonlyarray-type-in-typescript)
45. [How do you use the `Partial` utility type in TypeScript?](#q45-how-do-you-use-the-partial-utility-type-in-typescript)
46. [What is the `Required` utility type in TypeScript?](#q46-what-is-the-required-utility-type-in-typescript)
47. [How do you handle default values in TypeScript functions?](#q47-how-do-you-handle-default-values-in-typescript-functions)
48. [What is the `ReturnType` utility type in TypeScript?](#q48-what-is-the-returntype-utility-type-in-typescript)
49. [How do you use `instanceof` for type narrowing?](#q49-how-do-you-use-instanceof-for-type-narrowing)
50. [What is a `Symbol` type in TypeScript?](#q50-what-is-a-symbol-type-in-typescript)
51. [How do you use the `Tuple` type to handle fixed-length arrays?](#q51-how-do-you-use-the-tuple-type-to-handle-fixed-length-arrays)
52. [What is the `Function` type in TypeScript?](#q52-what-is-the-function-type-in-typescript)
53. [How do you use `typeof` for type assertions?](#q53-how-do-you-use-typeof-for-type-assertions)
54. [What is the difference between `declare` and `export` in TypeScript?](#q54-what-is-the-difference-between-declare-and-export-in-typescript)
55. [How do you use `keyof` to create a type that includes keys of an existing type?](#q55-how-do-you-use-keyof-to-create-a-type-that-includes-keys-of-an-existing-type)
56. [How do you handle overloading methods in TypeScript?](#q56-how-do-you-handle-overloading-methods-in-typescript)
57. [What is `Object` type in TypeScript?](#q57-what-is-object-type-in-typescript)
58. [How do you use the `Parameters` utility type in TypeScript?](#q58-how-do-you-use-the-parameters-utility-type-in-typescript)
59. [What is the `Exclude` utility type in TypeScript?](#q59-what-is-the-exclude-utility-type-in-typescript)
60. [How do you use the `Extract` utility type in TypeScript?](#q60-how-do-you-use-the-extract-utility-type-in-typescript)

---

## Q1: What is TypeScript?

**A1:** TypeScript is a statically typed superset of JavaScript that adds optional static types, interfaces, and modern ECMAScript features to JavaScript. It compiles down to plain JavaScript, which can run in any browser or environment that supports JavaScript.

---

## Q2: How do you define a variable in TypeScript?

**A2:** In TypeScript, you define a variable by specifying its type after the variable name. For example, a boolean variable might be defined with `boolean`, a number with `number`, and a string with `string`.

---

## Q3: What are the basic types in TypeScript?

**A3:** The basic types in TypeScript include `boolean`, `number`, `string`, `array`, `tuple`, `enum`, `any`, `void`, `null`, and `undefined`. These types are used to define the shape and behavior of variables and functions in TypeScript.

---

## Q4: What is the difference between `any` and `unknown`?

**A4:** 
- `any` allows a variable to bypass type checking entirely, meaning it can hold any type of value and is treated as such.
- `unknown`, on the other hand, is a safer alternative to `any` as it requires type checks before you can perform any operations on it. This ensures more robust type safety in your code.

---

## Q5: How do you define an interface in TypeScript?

**A5:** An interface in TypeScript defines the structure of an object, specifying the types of its properties. Interfaces are used to ensure that objects adhere to a specific structure, which is useful for type checking and documentation.

---

## Q6: What is the purpose of optional properties in interfaces?

**A6:** Optional properties in interfaces allow certain properties to be defined but not required when creating an object. This is useful for objects that may have some fields that are not always present, providing flexibility while still enforcing structure.

---

## Q7: How do you create a class in TypeScript?

**A7:** A class in TypeScript is created using the `class` keyword followed by the class name, properties, and methods. Classes can encapsulate data and behavior, and can be instantiated to create objects.

---

## Q8: What are access modifiers in TypeScript?

**A8:** Access modifiers control the visibility of class members. The three main access modifiers in TypeScript are:
- `public`: Accessible everywhere (this is the default).
- `private`: Accessible only within the class itself.
- `protected`: Accessible within the class and its subclasses.

---

## Q9: How do you implement inheritance in TypeScript?

**A9:** Inheritance in TypeScript is implemented using the `extends` keyword, allowing a class to inherit properties and methods from a parent class. This promotes code reuse and the creation of more complex and specific classes.

---

## Q10: What is a union type in TypeScript?

**A10:** A union type in TypeScript allows a variable to hold values of multiple types. It is defined using the pipe (`|`) symbol between types, enabling a variable to accept more than one type.

---

## Q11: What is an intersection type in TypeScript?

**A11:** An intersection type in TypeScript combines multiple types into one, meaning an object of this type will have all the properties of the intersected types. It is defined using the ampersand (`&`) symbol between types.

---

## Q12: How do you create and use generics in TypeScript?

**A12:** Generics in TypeScript allow you to create components that work with a variety of types instead of a single one. They are defined using a type variable, which acts as a placeholder for a type that is specified when the function or class is used.

---

## Q13: What is a tuple in TypeScript?

**A13:** A tuple in TypeScript is an array with a fixed number of elements, where each element can have a different type. This is useful for representing fixed structures like key-value pairs or other groupings of mixed data types.

---

## Q14: How does TypeScript handle enums?

**A14:** Enums in TypeScript allow you to define a set of named constants. They can be either numeric or string-based, and they provide a way to create a collection of related values that can be used in a type-safe manner.

---

## Q15: What is type assertion in TypeScript?

**A15:** Type assertion in TypeScript allows you to tell the compiler that you know the type of a variable better than it does. This is used when you want to override the type inference system, usually when you have more information about the type than the compiler does.

---

## Q16: How do you define a function in TypeScript?

**A16:** In TypeScript, functions are defined with a specified return type and parameter types. This ensures that the function behaves as expected and helps with catching errors at compile-time.

---

## Q17: What are the differences between interfaces and type aliases?

**A17:** 
- Interfaces are primarily used to define the structure of objects, and they can be extended or implemented by classes.
- Type aliases can represent more complex types, including union types, intersection types, and other advanced TypeScript types. Type aliases are more versatile, but interfaces are more specific to object structure.

---

## Q18: How do you handle null and undefined in TypeScript?

**A18:** TypeScript provides strict null and undefined checks with the `strictNullChecks` compiler option. When enabled, variables can only be assigned `null` or `undefined` if explicitly allowed. This helps in avoiding common runtime errors related to null or undefined values.

---

## Q19: What are decorators in TypeScript?

**A19:** Decorators in TypeScript are special functions that can be attached to classes, methods, accessors, properties, or parameters. They allow you to modify the behavior of these elements at runtime, and are often used in frameworks like Angular for dependency injection and metadata handling.

---

## Q20: How do you use TypeScript with React?

**A20:** TypeScript can be used with React by defining types for props and state, which ensures type safety in React components. It allows for better tooling and code completion in React projects, making it easier to catch errors and enforce consistent usage patterns.

---

## Q21: What are modules in TypeScript?

**A21:** Modules in TypeScript allow you to encapsulate code into separate files and namespaces. This promotes better organization and reuse of code across a project, and helps to avoid naming collisions.

---

## Q22: How do you export and import modules in TypeScript?

**A22:** In TypeScript, modules can be exported and imported using the `export` and `import` keywords. This allows different parts of an application to share and reuse code efficiently.

---

## Q23: What are namespaces in TypeScript?

**A23:** Namespaces in TypeScript are a way to group related code together under a single name, which helps in organizing large codebases. They provide a way to avoid naming collisions by encapsulating code within a named scope.

---

## Q24: How do you use async/await in TypeScript?

**A24:** Async/await is used in TypeScript to handle asynchronous operations in a more readable and maintainable way. It allows you to write asynchronous code that looks synchronous, making it easier to follow the logic and handle errors.

---

## Q25: What are ambient declarations in TypeScript?

**A25:** Ambient declarations in TypeScript allow you to describe the shape of code that is written elsewhere, such as in JavaScript libraries. They are usually found in `.d.ts` files and are used to provide type information for existing JavaScript code.

---

## Q26: How does TypeScript support JSX?

**A26:** TypeScript supports JSX by allowing you to write JSX syntax in `.tsx` files. This is primarily used with React, where TypeScript can provide type checking and tooling support for JSX elements, ensuring they are used correctly.

---

## Q27: What are the advantages of using TypeScript over JavaScript?

**A27:** The main advantages of TypeScript over JavaScript include:
- Static typing, which helps catch errors at compile time.
- Enhanced tooling and code completion, which improves developer productivity.
- Better support for modern ECMAScript features, while still being compatible with older JavaScript environments.
- Clearer, more maintainable code through the use of interfaces, classes, and modules.

---

## Q28: How do you handle errors in TypeScript?

**A28:** Error handling in TypeScript is done using try/catch blocks, similar to JavaScript. TypeScript's type system can also be used to define custom error types and ensure that functions properly handle or propagate errors.

---

## Q29: What is the difference between `let`, `var`, and `const` in TypeScript?

**A29:** 
- `let` is used to declare block-scoped variables.
- `var` declares function-scoped or globally-scoped variables, which can lead to issues in larger codebases.
- `const` declares block-scoped variables that cannot be reassigned, making it the preferred choice for defining constants.

---

## Q30: How do you configure the TypeScript compiler with `tsconfig.json`?

**A30:** The `tsconfig.json` file is used to configure the TypeScript compiler options, such as specifying the target ECMAScript version, module resolution strategy, and strict type checking options. This file allows you to customize the behavior of the TypeScript compiler for your project.

---

## Q31: What is the `void` type in TypeScript?

**A31:** The `void` type represents the absence of a value. It is commonly used for functions that do not return a value, indicating that the function performs an action but does not produce a result.

---

## Q32: How do you create a readonly property in TypeScript?

**A32:** You create a readonly property by using the `readonly` modifier in an interface or class. This ensures that the property cannot be modified after its initial assignment.

---

## Q33: What is a `never` type in TypeScript?

**A33:** The `never` type represents a value that never occurs. It is used for functions that never return (e.g., functions that throw an error or have infinite loops) and for variables that should not be assigned any value.

---

## Q34: How do you use TypeScript with existing JavaScript libraries?

**A34:** TypeScript can be used with existing JavaScript libraries by installing type definitions for those libraries, usually via the DefinitelyTyped repository (`@types/`). This allows TypeScript to understand and check the types used in the JavaScript library.

---

## Q35: What is a type guard in TypeScript?

**A35:** A type guard is a TypeScript feature that allows you to narrow down the type of a variable within a conditional block. Common examples include `typeof` checks, `instanceof` checks, and custom type guard functions.

---

## Q36: How do you create a custom type guard in TypeScript?

**A36:** A custom type guard is created by defining a function that returns a boolean value and asserts a type using a type predicate. This helps TypeScript understand the type of a variable within the function's scope.

---

## Q37: What is the `keyof` operator in TypeScript?

**A37:** The `keyof` operator is used to obtain the union of all property names of a given type. It helps in creating more flexible and type-safe code by restricting keys to those present in a type.

---

## Q38: How do you define a mapped type in TypeScript?

**A38:** Mapped types are defined using a combination of the `keyof` operator and a type transformation. They allow you to create a new type by applying a transformation to each property of an existing type.

---

## Q39: What is `type inference` in TypeScript?

**A39:** Type inference is the TypeScript compiler's ability to automatically deduce the type of a variable or expression based on its usage and context. This reduces the need for explicit type annotations in many cases.

---

## Q40: What are conditional types in TypeScript?

**A40:** Conditional types allow you to create types that depend on a condition. They use the syntax `T extends U ? X : Y` to define types based on whether a type `T` extends another type `U`, resulting in either type `X` or `Y`.

---

## Q41: How do you use `infer` in conditional types?

**A41:** The `infer` keyword allows you to introduce a type variable within a conditional type. It is used to capture and infer types within the true branch of a conditional type, providing more flexibility in type definitions.

---

## Q42: What is the purpose of `this` type in TypeScript?

**A42:** The `this` type allows you to specify the type of the current instance within methods or functions, ensuring that `this` is correctly typed in object-oriented programming scenarios.

---

## Q43: How do you use type intersections to merge types?

**A43:** Type intersections use the `&` operator to combine multiple types into one. This results in a type that has all properties from the intersected types, allowing for the creation of more complex and flexible type definitions.

---

## Q44: What is the `ReadonlyArray` type in TypeScript?

**A44:** `ReadonlyArray` is a utility type that represents an array whose elements cannot be modified. It provides a way to ensure that an array remains immutable.

---

## Q45: How do you use the `Partial` utility type in TypeScript?

**A45:** The `Partial` utility type creates a new type where all properties of the original type are optional. This is useful for scenarios where you want to allow partial updates to objects.

---

## Q46: What is the `Required` utility type in TypeScript?

**A46:** The `Required` utility type creates a new type where all properties of the original type are required. It is the opposite of the `Partial` utility type.

---

## Q47: How do you handle default values in TypeScript functions?

**A47:** Default values in TypeScript functions are specified by assigning a default value to a parameter in the function signature. This provides a fallback value if no argument is provided.

---

## Q48: What is the `ReturnType` utility type in TypeScript?

**A48:** The `ReturnType` utility type extracts the return type of a function type. It is useful for creating types based on the result of a function, ensuring consistency and type safety.

---

## Q49: How do you use `instanceof` for type narrowing?

**A49:** The `instanceof` operator is used to narrow down the type of an object based on its constructor. It helps TypeScript infer the specific type of an object in conditional blocks.

---

## Q50: What is a `Symbol` type in TypeScript?

**A50:** The `Symbol` type represents a unique and immutable value that is often used as object property keys. It ensures that properties with `Symbol` keys are distinct and avoid conflicts.

---

## Q51: How do you use the `Tuple` type to handle fixed-length arrays?

**A51:** The `Tuple` type allows you to define arrays with a fixed number of elements where each element can have a different type. It is useful for scenarios where the structure of the array is known and fixed.

---

## Q52: What is the `Function` type in TypeScript?

**A52:** The `Function` type is a general type for function values. It can be used to represent any function, but it is usually better to specify the function signature for more precise type checking.

---

## Q53: How do you use `typeof` for type assertions?

**A53:** The `typeof` operator can be used for type assertions to check the type of a value at runtime. This is helpful for ensuring type safety when working with dynamically typed values.

---

## Q54: What is the difference between `declare` and `export` in TypeScript?

**A54:** 
- `declare` is used to declare variables, functions, or classes that exist outside the TypeScript file, typically in ambient declarations or type definitions.
- `export` is used to make variables, functions, classes, or interfaces available to other modules within a TypeScript project.

---

## Q55: How do you use `keyof` to create a type that includes keys of an existing type?

**A55:** The `keyof` operator creates a union type of the keys of an existing type. It is used to create types based on the property names of another type, enhancing type safety and flexibility in type operations.

---

## Q56: How do you handle overloading methods in TypeScript?

**A56:** Method overloading in TypeScript is handled by defining multiple signatures for a single method, each with different parameter types. The implementation must match one of these signatures, allowing for different ways to call the method.

---

## Q57: What is `Object` type in TypeScript?

**A57:** The `Object` type represents any value that is not a primitive type (`number`, `string`, `boolean`, `symbol`, `null`, or `undefined`). It is a more general type that can be used when you need to work with complex objects.

---

## Q58: How do you use the `Parameters` utility type in TypeScript?

**A58:** The `Parameters` utility type extracts the parameter types of a function type as a tuple. It is useful for obtaining the types of arguments passed to a function, making it easier to work with function signatures.

---

## Q59: What is the `Exclude` utility type in TypeScript?

**A59:** The `Exclude` utility type creates a new type by excluding specific types from an existing union type. It is useful for filtering out unwanted types from a union, resulting in a more precise type.

---

## Q60: How do you use the `Extract` utility type in TypeScript?

**A60:** The `Extract` utility type creates a new type by extracting specific types from a union type. It is useful for obtaining a subset of types that match certain criteria, improving type safety and precision.
