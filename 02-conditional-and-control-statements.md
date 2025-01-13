# [JavaScript Tutorial](README.md): Conditional Statements and Looping
---

## Table of Contents

1. [Conditional Statements](#conditional-statements)
   - [What are Conditional Statements?](#what-are-conditional-statements)
   - [Types of Conditional Statements](#types-of-conditional-statements)
     - [if Statement](#if-statement)
     - [if-else Statement](#if-else-statement)
     - [if-else-if Ladder](#if-else-if-ladder)
     - [Nested if](#nested-if)
     - [Switch Statement](#switch-statement)
     - [Ternary Operator](#ternary-operator)
2. [Looping in JavaScript](#looping-in-javascript)
   - [What are Loops?](#what-are-loops)
   - [Types of Loops](#types-of-loops)
     - [for Loop](#for-loop)
     - [while Loop](#while-loop)
     - [do-while Loop](#do-while-loop)
     - [for...in Loop](#forin-loop)
     - [for...of Loop](#forof-loop)
     - [break and continue Statements](#break-and-continue-statements)

---

## Conditional Statements

### What are Conditional Statements?

**Conditional statements** allow a program to make decisions based on specific conditions or expressions. They enable the code to execute different blocks depending on whether the condition evaluates to `true` or `false`.

In simpler terms:
- Conditional statements act like decision-makers in your program.
- They help control the flow of execution based on logical conditions.

---

### Types of Conditional Statements

#### 1. if Statement

The `if` statement is the simplest form of conditional logic. It executes a block of code only when the condition evaluates to `true`.

**Definition**:  
An `if` statement checks a condition, and if it's true, it runs the code inside the block.

#### Syntax
```javascript
if (condition) {
  // Code to execute if the condition is true
}
```

#### Example
```javascript
let age = 20;
if (age >= 18) {
  console.log("You are eligible to vote.");
}
// Output: You are eligible to vote.
```

**Explanation**:  
- The condition `age >= 18` is evaluated.
- Since `age` is `20`, the condition is `true`, and the code inside the `if` block executes.

---

#### 2. if-else Statement

The `if-else` statement adds an alternate block of code to execute when the condition is `false`.

**Definition**:  
An `if-else` statement provides a fallback for cases where the condition is not met.

#### Syntax
```javascript
if (condition) {
  // Code to execute if condition is true
} else {
  // Code to execute if condition is false
}
```

#### Example
```javascript
let age = 16;
if (age >= 18) {
  console.log("You are eligible to vote.");
} else {
  console.log("You are not eligible to vote.");
}
// Output: You are not eligible to vote.
```

**Explanation**:  
- The condition `age >= 18` is `false` because `age` is `16`.
- The code in the `else` block executes.

---

#### 3. if-else-if Ladder

The `if-else-if` ladder is used when you need to test multiple conditions sequentially.

**Definition**:  
An `if-else-if` ladder evaluates multiple conditions in order and executes the block of the first condition that is true.

#### Syntax
```javascript
if (condition1) {
  // Code if condition1 is true
} else if (condition2) {
  // Code if condition2 is true
} else {
  // Code if no condition is true
}
```

#### Example
```javascript
let score = 85;
if (score >= 90) {
  console.log("Grade: A");
} else if (score >= 75) {
  console.log("Grade: B");
} else {
  console.log("Grade: C");
}
// Output: Grade: B
```

**Explanation**:  
- The first condition (`score >= 90`) is `false`.
- The second condition (`score >= 75`) is `true`, so the corresponding block executes.

---

#### 4. Nested if

**Definition**:  
A `nested if` is an `if` statement placed inside another `if` statement. It allows for more complex decision-making.

#### Example
```javascript
let age = 25;
let hasID = true;

if (age >= 18) {
  if (hasID) {
    console.log("You can enter the club.");
  } else {
    console.log("Please provide an ID.");
  }
} else {
  console.log("You are not allowed to enter.");
}
// Output: You can enter the club.
```

**Explanation**:  
- The outer `if` checks if the person is at least 18 years old.
- The inner `if` checks if the person has an ID.

---

#### 5. Switch Statement

**Definition**:  
The `switch` statement evaluates an expression and matches it against multiple cases. It is useful when comparing a single value against many possibilities.

#### Syntax
```javascript
switch (expression) {
  case value1:
    // Code for case value1
    break;
  case value2:
    // Code for case value2
    break;
  default:
    // Code if no case matches
}
```

#### Example
```javascript
let day = 3;

switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  default:
    console.log("Invalid day");
}
// Output: Wednesday
```

**Explanation**:  
- The `day` variable matches `case 3`, so the block under it executes.
- The `break` statement prevents further cases from being checked.

---

#### 6. Ternary Operator

**Definition**:  
A shorthand for `if-else` statements, the ternary operator evaluates a condition and returns one of two values.

#### Syntax
```javascript
condition ? expressionIfTrue : expressionIfFalse;
```

#### Example
```javascript
let age = 20;
let result = (age >= 18) ? "Adult" : "Minor";
console.log(result);
// Output: Adult
```

**Explanation**:  
- The condition `age >= 18` is `true`, so `Adult` is assigned to `result`.

---

## Looping in JavaScript

### What are Loops?

**Definition**:  
Loops are constructs that allow you to execute a block of code multiple times, either for a specific number of iterations or until a condition is met.

---

### Types of Loops

#### 1. for Loop

**Definition**:  
The `for` loop repeats a block of code a specific number of times.

#### Syntax
```javascript
for (initialization; condition; increment/decrement) {
  // Code to execute
}
```

#### Example
```javascript
for (let i = 1; i <= 5; i++) {
  console.log(`Iteration ${i}`);
}
// Output: Iteration 1, Iteration 2, ..., Iteration 5
```

**Explanation**:  
1. The `initialization` (`let i = 1`) runs once before the loop starts.
2. The `condition` (`i <= 5`) is checked before each iteration.
3. The `increment` (`i++`) runs after each iteration.

---

#### 2. while Loop

**Definition**:  
The `while` loop executes a block of code as long as the condition is `true`.

#### Syntax
```javascript
while (condition) {
  // Code to execute
}
```

#### Example
```javascript
let i = 1;
while (i <= 5) {
  console.log(`Count: ${i}`);
  i++;
}
// Output: Count: 1, Count: 2, ..., Count: 5
```

---

#### 3. do-while Loop

**Definition**:  
The `do-while` loop executes the code block at least once, then repeats as long as the condition is `true`.

#### Syntax
```javascript
do {
  // Code to execute
} while (condition);
```

#### Example
```javascript
let i = 1;
do {
  console.log(`Count: ${i}`);
  i++;
} while (i <= 5);
// Output: Count: 1, Count: 2, ..., Count: 5
```

---

#### 4. for...in Loop

**Definition**:  
The `for...in` loop iterates over the properties of an object or indices of an array.

#### Example with Object
```javascript
let user = { name: "Alice", age: 25 };
for (let key in user) {
  console.log(`${key}: ${user[key]}`);
}
// Output: name: Alice, age: 25
```

---

#### 5. for...of Loop

**Definition**:  
The `for...of` loop iterates over iterable objects like arrays, strings, etc.

#### Example with Array
```javascript
let arr = [10, 20, 30];
for (let value of arr) {
  console.log(value); // Output: 10, 20, 30
}
```

---

#### 6. break and continue Statements

- **`break`**: Exits the loop prematurely.
- **`continue`**: Skips the current iteration and proceeds to the next.

#### Example with `break`
```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) break;
  console.log(i); // Output: 1, 2
}
```

#### Example with `continue`
```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i); // Output: 1, 2, 4, 5
}
```

---
