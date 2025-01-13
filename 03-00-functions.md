# JavaScript Functions: A Comprehensive Guide
  ### Go back to [JavaScript Tutorial](README.md)
---

## What are Functions in JavaScript?

### Definition
A **function** in JavaScript is a reusable block of code designed to perform a specific task. Functions help in:
- **Code Reusability**: Write once, use multiple times.
- **Modularity**: Divide the program into smaller, manageable parts.
- **Dynamic Behavior**: Accept inputs (parameters) and return outputs.

### Syntax
```javascript
function functionName(parameters) {
  // Function body: code to execute
  return value; // Optional
}
```

### Example
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet("Alice")); // Output: Hello, Alice!
```

### Why Functions Matter
Without functions, code would become repetitive and hard to maintain. Imagine having to write the same logic every time you need it. Functions make code concise and structured.

---

## Built-in Functions

### Definition
**Built-in functions** are pre-defined by JavaScript to perform specific tasks. They simplify common operations like string manipulation, math calculations, or date formatting.

### Examples of Built-in Functions

1. **`console.log()`**
   - Used to print messages or outputs to the console.
   - Example:
     ```javascript
     console.log("Hello, World!"); 
     // Output: Hello, World!
     ```

2. **`Math.max()`**
   - Finds the largest number from a list.
   - Example:
     ```javascript
     console.log(Math.max(10, 20, 30)); 
     // Output: 30
     ```

3. **`parseInt()`**
   - Converts a string to an integer.
   - Example:
     ```javascript
     console.log(parseInt("42")); 
     // Output: 42
     ```

4. **`Date()`**
   - Returns the current date and time.
   - Example:
     ```javascript
     let now = new Date();
     console.log(now);
     ```

### Problem Example
Find the square root of a number using a built-in function:
```javascript
let number = 64;
let result = Math.sqrt(number);
console.log(`Square root of ${number} is ${result}`);
// Output: Square root of 64 is 8
```

---

## Regular Functions

### Definition
A **regular function** is a named function declared using the `function` keyword. It can take parameters and return a value.

### Syntax
```javascript
function functionName(parameters) {
  // Function body
  return value; // Optional
}
```

### Example
```javascript
function add(a, b) {
  return a + b;
}

console.log(add(5, 3)); // Output: 8
```

### Problem Example: Find the factorial of a number using a regular function.
```javascript
function factorial(n) {
  let result = 1;
  for (let i = 1; i <= n; i++) {
    result *= i;
  }
  return result;
}

console.log(factorial(5)); // Output: 120
```

---

## Passing Parameters to Functions

### Definition
**Parameters** are variables passed to a function that allow the function to accept dynamic inputs.

### Syntax
```javascript
function functionName(parameter1, parameter2) {
  // Function body
}
```

### Example
```javascript
function multiply(a, b) {
  return a * b;
}

console.log(multiply(4, 5)); // Output: 20
```

### Explanation
- `a` and `b` are parameters that hold the values `4` and `5` during execution.
- Functions can accept multiple parameters or none at all.

### Problem Example: Write a function that greets a user in different languages.
```javascript
function greetUser(name, language) {
  if (language === "English") {
    return `Hello, ${name}!`;
  } else if (language === "Spanish") {
    return `Hola, ${name}!`;
  } else {
    return `Hi, ${name}!`;
  }
}

console.log(greetUser("Alice", "Spanish")); // Output: Hola, Alice!
```

---

## Return Value

### Definition
A function can return a value using the `return` statement. The returned value can be stored in a variable or used directly.

### Example
```javascript
function square(number) {
  return number * number;
}

let result = square(4);
console.log(result); // Output: 16
```

---

## Anonymous Functions

### Definition
An **anonymous function** is a function without a name. It is usually assigned to a variable or passed as an argument.

### Syntax
```javascript
let variableName = function(parameters) {
  // Function body
};
```

### Example: Assigning an anonymous function to a variable
```javascript
let greet = function(name) {
  return `Hello, ${name}!`;
};

console.log(greet("Alice")); // Output: Hello, Alice!
```

### Problem Example: Sort an array using an anonymous function.
```javascript
let numbers = [10, 5, 8, 1];
numbers.sort(function(a, b) {
  return a - b;
});

console.log(numbers); // Output: [1, 5, 8, 10]
```

---

## Arrow Functions

### Definition
An **arrow function** is a shorter syntax for writing functions, introduced in ES6. It inherits the `this` context from its surrounding scope.

### Syntax
```javascript
(parameters) => {
  // Function body
  return value; // Optional
};
```

### Example: Arrow function to calculate square
```javascript
let square = (number) => number * number;
console.log(square(4)); // Output: 16
```

### Problem Example: Double each number in an array using arrow functions.
```javascript
let numbers = [1, 2, 3, 4];
let doubled = numbers.map(num => num * 2);

console.log(doubled); // Output: [2, 4, 6, 8]
```

---

## Differences Between Function Types

| **Feature**        | **Regular Functions**                     | **Anonymous Functions**              | **Arrow Functions**                 |
|---------------------|-------------------------------------------|---------------------------------------|--------------------------------------|
| **Syntax**          | `function name(params) {}`               | `function(params) {}`                | `(params) => {}`                    |
| **Name**            | Named                                    | Not named                            | Not named                           |
| **Context (`this`)**| Uses its own `this`                      | Uses its own `this`                  | Inherits `this` from the parent scope |
| **Usage**           | Reusable and named                       | Used as expressions or callbacks     | Short, concise functions            |
| **Example**         | `function add(a, b) { return a + b; }`   | `let add = function(a, b) { ... };`  | `let add = (a, b) => a + b;`        |

---

## Key Takeaways

1. **Functions** are essential for reusability and modularity.
2. Use **built-in functions** for common tasks.
3. **Regular functions** are ideal for structured, named tasks.
4. **Anonymous functions** and **arrow functions** are useful for callbacks and concise logic.
5. Understanding function types and contexts is crucial for mastering JavaScript.

---
