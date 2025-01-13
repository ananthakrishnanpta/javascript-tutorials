## 1. **What Are User-Defined Functions?**

A **user-defined function** is a reusable block of code written by a programmer to perform a specific task. Unlike built-in functions (like `Math.max()`), these functions are explicitly defined by you.

### Syntax
```javascript
function functionName(parameters) {
    // Code to execute
    return value; // Optional, specifies the output of the function
}
```

---

## 2. **Understanding Scope in JavaScript**

### Definition
**Scope** defines the accessibility of variables, functions, and objects in JavaScript. In simpler terms, scope determines where in your code a variable or function can be accessed.

### Types of Scope in JavaScript
1. **Global Scope**: Variables declared outside any function or block are accessible everywhere in the code.
2. **Local Scope**: Variables declared within a function or block are only accessible within that specific function or block.
3. **Block Scope**: Variables declared with `let` and `const` inside a block (`{}`) are confined to that block.
4. **Function Scope**: Variables declared with `var` are accessible within the entire function they are defined in.

---

### Scope Examples

#### Global Scope
```javascript
let globalVar = "I am global";

function showGlobal() {
    console.log(globalVar); // Accessible
}
showGlobal(); // Output: I am global
```

#### Local Scope
```javascript
function localScope() {
    let localVar = "I am local";
    console.log(localVar); // Accessible
}
localScope();
console.log(localVar); // Error: localVar is not defined
```

#### Block Scope
```javascript
{
    let blockScoped = "Only accessible in this block";
    console.log(blockScoped); // Accessible
}
console.log(blockScoped); // Error: blockScoped is not defined
```

#### Function Scope
```javascript
function functionScope() {
    if (true) {
        var functionScopedVar = "I am function scoped";
    }
    console.log(functionScopedVar); // Accessible
}
functionScope();
```

---

### The Difference Between `var`, `let`, and `const` in Scope

| Keyword | Scope           | Redeclaration | Reassignment | Hoisting  |
|---------|------------------|---------------|--------------|-----------|
| `var`   | Function         | Allowed       | Allowed      | Yes       |
| `let`   | Block            | Not Allowed   | Allowed      | No        |
| `const` | Block            | Not Allowed   | Not Allowed  | No        |

---

## 3. **Advanced Function Techniques**

### 3.1 Recursion
**Recursion** is when a function calls itself. It's used for problems that can be broken down into smaller, similar problems.

#### Example: Factorial
```javascript
function factorial(n) {
    if (n === 0) return 1; // Base case
    return n * factorial(n - 1); // Recursive call
}
console.log(factorial(5)); // Output: 120
```

#### Example: Fibonacci
```javascript
function fibonacci(n) {
    if (n <= 1) return n; // Base case
    return fibonacci(n - 1) + fibonacci(n - 2); // Recursive call
}
console.log(fibonacci(6)); // Output: 8
```

---

### 3.2 Memoization
**Memoization** is an optimization technique that stores the results of expensive function calls for reuse.

#### Example
```javascript
function memoizedFactorial() {
    const cache = {};
    return function factorial(n) {
        if (n in cache) return cache[n];
        if (n === 0) return 1;
        cache[n] = n * factorial(n - 1);
        return cache[n];
    };
}
const factorial = memoizedFactorial();
console.log(factorial(5)); // Output: 120
```

---

### 3.3 Function Currying
**Currying** transforms a function with multiple arguments into a sequence of functions that each accept a single argument.

#### Example
```javascript
function curriedAdd(a) {
    return function(b) {
        return function(c) {
            return a + b + c;
        };
    };
}
console.log(curriedAdd(1)(2)(3)); // Output: 6
```

---

### 3.4 Closures
A **closure** is a function that "remembers" the variables from its outer scope even after the outer function has executed.

#### Example
```javascript
function outerFunction(outerVar) {
    return function innerFunction(innerVar) {
        console.log(`Outer: ${outerVar}, Inner: ${innerVar}`);
    };
}
const closure = outerFunction("outside");
closure("inside"); // Output: Outer: outside, Inner: inside
```

---

## 4. **Return Types in Functions**

Functions in JavaScript can return:
1. **Primitive values** (e.g., numbers, strings).
2. **Objects**.
3. **Functions**.

### Examples

#### Returning a Primitive
```javascript
function sum(a, b) {
    return a + b;
}
console.log(sum(2, 3)); // Output: 5
```

#### Returning an Object
```javascript
function createUser(name, age) {
    return { name, age };
}
console.log(createUser("Alice", 30)); // Output: { name: 'Alice', age: 30 }
```

#### Returning a Function
```javascript
function multiplier(factor) {
    return function(number) {
        return number * factor;
    };
}
const double = multiplier(2);
console.log(double(5)); // Output: 10
```

---

## 5. **Advanced Use Cases**

### 5.1 Throttling
Throttling limits the execution of a function to once every specified interval.
```javascript
function throttle(func, limit) {
    let inThrottle;
    return function () {
        if (!inThrottle) {
            func.apply(this, arguments);
            inThrottle = true;
            setTimeout(() => (inThrottle = false), limit);
        }
    };
}
const log = () => console.log("Throttled!");
const throttledLog = throttle(log, 2000);
throttledLog();
```

### 5.2 Debouncing
Debouncing delays the execution of a function until a specified time has passed since the last call.
```javascript
function debounce(func, delay) {
    let timeout;
    return function () {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, arguments), delay);
    };
}
const log = () => console.log("Debounced!");
const debouncedLog = debounce(log, 2000);
debouncedLog();
```

---
