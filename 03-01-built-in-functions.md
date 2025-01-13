# JavaScript Built-in Functions

  ### Go back to [JavaScript Tutorial](README.md)

JavaScript provides a variety of built-in functions for different tasks. These are organized into categories based on their use cases:

1. **Global Functions**  
2. **String Functions**  
3. **Array Functions**  
4. **Math Functions**  
5. **Date Functions**  
6. **Object Functions**  
7. **Utility Functions**  

---

## 1. Global Functions

Global functions are available throughout the program and can be accessed directly without importing any module.

### 1.1 `parseInt()`
- **Description**: Converts a string to an integer.
- **Syntax**: `parseInt(string, radix)`
  - `string`: The string to parse.
  - `radix`: The base of the numeral system (optional).
- **Example**:
  ```javascript
  console.log(parseInt("42"));       // Output: 42
  console.log(parseInt("101", 2));  // Output: 5 (binary to decimal)
  ```

### 1.2 `parseFloat()`
- **Description**: Converts a string to a floating-point number.
- **Example**:
  ```javascript
  console.log(parseFloat("3.14"));  // Output: 3.14
  console.log(parseFloat("10.5px"));// Output: 10.5
  ```

### 1.3 `isNaN()`
- **Description**: Checks if a value is NaN (Not-a-Number).
- **Example**:
  ```javascript
  console.log(isNaN("hello"));   // Output: true
  console.log(isNaN(123));       // Output: false
  ```

### 1.4 `Number()`
- **Description**: Converts a value to a number.
- **Example**:
  ```javascript
  console.log(Number("42"));     // Output: 42
  console.log(Number(true));     // Output: 1
  ```

---

## 2. String Functions

String functions are used to manipulate and analyze text data.

### 2.1 `charAt()`
- **Description**: Returns the character at a specific index.
- **Example**:
  ```javascript
  let str = "Hello";
  console.log(str.charAt(1));  // Output: e
  ```

### 2.2 `toUpperCase()` / `toLowerCase()`
- **Description**: Converts a string to uppercase or lowercase.
- **Example**:
  ```javascript
  let text = "JavaScript";
  console.log(text.toUpperCase()); // Output: JAVASCRIPT
  console.log(text.toLowerCase()); // Output: javascript
  ```

### 2.3 `indexOf()`
- **Description**: Returns the position of the first occurrence of a substring.
- **Example**:
  ```javascript
  let str = "Hello, world!";
  console.log(str.indexOf("world")); // Output: 7
  ```

### 2.4 `substring()`
- **Description**: Extracts a portion of the string.
- **Syntax**: `string.substring(start, end)`
- **Example**:
  ```javascript
  let str = "JavaScript";
  console.log(str.substring(0, 4)); // Output: Java
  ```

---

## 3. Array Functions

Array functions help in manipulating and analyzing arrays.

### 3.1 `push()` / `pop()`
- **Description**: Adds or removes elements from the end of an array.
- **Example**:
  ```javascript
  let arr = [1, 2, 3];
  arr.push(4); 
  console.log(arr);  // Output: [1, 2, 3, 4]
  arr.pop();
  console.log(arr);  // Output: [1, 2, 3]
  ```

### 3.2 `shift()` / `unshift()`
- **Description**: Adds or removes elements from the beginning of an array.
- **Example**:
  ```javascript
  let arr = [1, 2, 3];
  arr.unshift(0); 
  console.log(arr);  // Output: [0, 1, 2, 3]
  arr.shift();
  console.log(arr);  // Output: [1, 2, 3]
  ```

### 3.3 `map()`
- **Description**: Creates a new array by applying a function to each element.
- **Example**:
  ```javascript
  let nums = [1, 2, 3];
  let squares = nums.map(num => num * num);
  console.log(squares); // Output: [1, 4, 9]
  ```

### 3.4 `filter()`
- **Description**: Filters an array based on a condition.
- **Example**:
  ```javascript
  let nums = [1, 2, 3, 4];
  let evenNums = nums.filter(num => num % 2 === 0);
  console.log(evenNums); // Output: [2, 4]
  ```

---

## 4. Math Functions

Math functions perform mathematical operations.

### 4.1 `Math.round()`
- **Description**: Rounds a number to the nearest integer.
- **Example**:
  ```javascript
  console.log(Math.round(4.5)); // Output: 5
  ```

### 4.2 `Math.random()`
- **Description**: Generates a random number between 0 and 1.
- **Example**:
  ```javascript
  console.log(Math.random()); // Output: 0.123456 (random)
  ```

### 4.3 `Math.pow()`
- **Description**: Returns the base raised to the power of the exponent.
- **Example**:
  ```javascript
  console.log(Math.pow(2, 3)); // Output: 8
  ```

---

## 5. Date Functions

Date functions handle date and time operations.

### 5.1 `Date()`
- **Description**: Returns the current date and time.
- **Example**:
  ```javascript
  let now = new Date();
  console.log(now); // Output: Fri Jan 10 2025 14:00:00 GMT+0530 (IST)
  ```

### 5.2 `getFullYear()`
- **Description**: Returns the year from a `Date` object.
- **Example**:
  ```javascript
  let now = new Date();
  console.log(now.getFullYear()); // Output: 2025
  ```

---

## 6. Object Functions

Object functions work with JavaScript objects.

### 6.1 `Object.keys()`
- **Description**: Returns an array of an object's keys.
- **Example**:
  ```javascript
  let obj = { a: 1, b: 2 };
  console.log(Object.keys(obj)); // Output: ["a", "b"]
  ```

### 6.2 `Object.values()`
- **Description**: Returns an array of an object's values.
- **Example**:
  ```javascript
  let obj = { a: 1, b: 2 };
  console.log(Object.values(obj)); // Output: [1, 2]
  ```

---

## 7. Utility Functions

### 7.1 `setTimeout()`
- **Description**: Executes a function after a delay.
- **Example**:
  ```javascript
  setTimeout(() => {
    console.log("Executed after 2 seconds");
  }, 2000);
  ```

### 7.2 `setInterval()`
- **Description**: Repeatedly executes a function at specified intervals.
- **Example**:
  ```javascript
  let count = 0;
  let interval = setInterval(() => {
    count++;
    console.log(`Count: ${count}`);
    if (count === 5) clearInterval(interval);
  }, 1000);
  ```

---
