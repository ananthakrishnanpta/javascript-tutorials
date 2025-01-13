# [JavaScript Tutorial](README.md)

---

## Table of Contents

1. [JavaScript History and Features](#javascript-history-and-features)
2. [Types of JavaScript](#types-of-javascript)
3. [Print Hello World](#print-hello-world)
4. [Comments](#comments)
5. [var, let, and const Keywords & Scopes](#var-let-and-const-keywords--scopes)
6. [Variable Hoisting](#variable-hoisting)
7. [Datatypes](#datatypes)
8. [Operators](#operators)

---

## JavaScript History and Features

### History

JavaScript was created in **1995** by **Brendan Eich** at Netscape. Here’s a brief timeline:
- **1995**: Initially named **Mocha**.
- **1996**: Renamed to **LiveScript** and then **JavaScript**.
- **1997**: Standardized as **ECMAScript (ES)**.
- **Present**: Continuously evolving with newer features (e.g., ES6 in 2015).

### Features

1. **Lightweight and Interpreted**: Runs directly in the browser without requiring compilation.
2. **Dynamic Typing**: Variable types are determined at runtime.
3. **First-Class Functions**: Functions can be assigned to variables, passed as arguments, or returned from other functions.
4. **Cross-Platform**: Runs in browsers and on servers (e.g., Node.js).

---

## Types of JavaScript

JavaScript is categorized into two main types:

### 1. **Client-Side JavaScript (CSJS)**
- Executes in the browser.
- Handles user interaction, DOM manipulation, and events.
- Example:
  ```javascript
  document.getElementById("demo").innerHTML = "Hello, Client-Side JS!";
  ```

### 2. **Server-Side JavaScript (SSJS)**
- Executes on a server, commonly using **Node.js**.
- Handles backend logic, API creation, and database interaction.
- Example:
  ```javascript
  const http = require("http");
  http.createServer((req, res) => {
    res.write("Hello, Server-Side JS!");
    res.end();
  }).listen(8080);
  ```

---

## Print Hello World

The classic "Hello, World!" program demonstrates basic syntax.

### Example
```javascript
console.log("Hello, World!");
```

### Explanation
- `console.log()` prints output to the browser's console.
- To see the output, open **Developer Tools** (`F12` or `Ctrl+Shift+I`) and go to the **Console** tab.

---

## Comments

Comments are used to make code more readable.

### Single-Line Comments
```javascript
// This is a single-line comment
console.log("Single-line comments are ignored by JavaScript.");
```

### Multi-Line Comments
```javascript
/*
  This is a multi-line comment.
  Useful for longer explanations or disabling multiple lines.
*/
console.log("Multi-line comments are also ignored.");
```

---

## var, let, and const Keywords & Scopes

JavaScript provides three ways to declare variables: **var**, **let**, and **const**.

---

### var

- **Function-Scoped**: Accessible throughout the function where it is declared.
- Can be **redeclared** and **reassigned**.

#### Example: Function Scope
```javascript
function exampleVar() {
  if (true) {
    var x = 10; // Declared inside a block
  }
  console.log(x); // Output: 10 (accessible outside the block)
}
exampleVar();
```

#### Example: Redeclaration
```javascript
var a = 5;
var a = 10; // Allowed
console.log(a); // Output: 10
```

---

### let

- **Block-Scoped**: Accessible only within the `{}` block where it is defined.
- Cannot be **redeclared** in the same block but can be **reassigned**.

#### Example: Block Scope
```javascript
if (true) {
  let y = 20;
  console.log(y); // Output: 20
}
// console.log(y); // Error: y is not defined
```

#### Example: No Redeclaration
```javascript
let z = 15;
// let z = 25; // Error: Cannot redeclare variable 'z'
z = 25; // Reassignment allowed
console.log(z); // Output: 25
```

---

### const

- **Block-Scoped**: Like `let`, but the value cannot be **reassigned**.
- Must be initialized during declaration.

#### Example
```javascript
const pi = 3.14;
// pi = 3.14159; // Error: Assignment to constant variable
console.log(pi); // Output: 3.14
```

---

### Comparison of var, let, and const
| Feature           | var          | let          | const         |
|--------------------|--------------|--------------|---------------|
| Scope             | Function     | Block        | Block         |
| Redeclaration     | Allowed      | Not Allowed  | Not Allowed   |
| Reassignment      | Allowed      | Allowed      | Not Allowed   |
| Initialization    | Optional     | Optional     | Mandatory     |

---

## Variable Hoisting

**Hoisting** refers to JavaScript's behavior of moving declarations to the top of their scope.

### Example: Hoisting with `var`
```javascript
console.log(a); // Output: undefined (declaration hoisted, not initialization)
var a = 5;
console.log(a); // Output: 5
```

### Example: Hoisting with `let` and `const`
```javascript
// console.log(b); // Error: Cannot access 'b' before initialization
let b = 10;
console.log(b); // Output: 10
```

---

## Datatypes

JavaScript provides two main categories of data types:

### 1. Primitive Datatypes
- **String**:
  ```javascript
  let name = "Alice";
  console.log(typeof name); // Output: string
  ```

- **Number**:
  ```javascript
  let age = 25;
  console.log(typeof age); // Output: number
  ```

- **Boolean**:
  ```javascript
  let isActive = true;
  console.log(typeof isActive); // Output: boolean
  ```

- **Undefined**:
  ```javascript
  let value;
  console.log(typeof value); // Output: undefined
  ```

- **Null**:
  ```javascript
  let empty = null;
  console.log(typeof empty); // Output: object (a known quirk in JavaScript)
  ```

- **Symbol**:
  ```javascript
  let uniqueID = Symbol("id");
  console.log(typeof uniqueID); // Output: symbol
  ```

---

### 2. Non-Primitive Datatypes
- **Object**:
  ```javascript
  let user = { name: "Alice", age: 25 };
  console.log(typeof user); // Output: object
  ```

---

## Operators

### Arithmetic Operators
```javascript
let a = 10, b = 3;
console.log(a + b); // 13
console.log(a - b); // 7
console.log(a * b); // 30
console.log(a / b); // 3.333...
console.log(a % b); // 1
```

### Comparison Operators
```javascript
let x = 10, y = "10";
console.log(x == y);  // true (loose equality)
console.log(x === y); // false (strict equality)
```

### Logical Operators
```javascript
console.log(true && false); // false
console.log(true || false); // true
console.log(!true);         // false
```

---
