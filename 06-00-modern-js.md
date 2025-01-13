# Modern JavaScript: Advanced Features
---

## 1. **Template Strings (Template Literals)**

**Definition**: Template strings (also called template literals) are a feature introduced in ECMAScript 6 (ES6) that allows you to embed expressions inside strings. They provide an easier way to work with strings and can span multiple lines without the need for escape characters.

### **Basic Syntax**
Template strings are enclosed in backticks (`\``), and you can embed expressions using `${}`.

### **Basic Example:**
```javascript
let name = "John";
let age = 25;
let greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting);
// Output: Hello, my name is John and I am 25 years old.
```

### **Multi-line Strings Example:**
```javascript
let message = `This is a message
spanning multiple lines.
It makes code more readable.`;
console.log(message);
```

### **Expression Inside Template Literals:**
You can use variables, arithmetic operations, or even function calls inside template strings.

```javascript
let num1 = 5;
let num2 = 10;
let result = `The sum of ${num1} and ${num2} is ${num1 + num2}.`;
console.log(result);
// Output: The sum of 5 and 10 is 15.
```

**Real-World Scenario**: Template literals are useful in generating dynamic HTML content or rendering a string with variable data, like building messages, invoices, or content in a web application.

---

## 2. **Destructuring Arrays and Objects**

**Definition**: Destructuring allows you to unpack values from arrays or properties from objects into distinct variables. It simplifies your code by allowing you to extract multiple values from complex structures in a single statement.

### **Array Destructuring:**

#### **Basic Syntax:**
```javascript
let arr = [1, 2, 3];
let [a, b, c] = arr;
console.log(a, b, c);  // Output: 1 2 3
```

#### **Skipping Items:**
```javascript
let arr = [1, 2, 3, 4];
let [, , c] = arr;  // Skips the first two elements
console.log(c);  // Output: 3
```

#### **Default Values:**
```javascript
let arr = [1, 2];
let [a, b = 5] = arr;  // b has a default value of 5
console.log(b);  // Output: 2
```

#### **Rest Pattern:**
```javascript
let arr = [1, 2, 3, 4];
let [first, second, ...rest] = arr;
console.log(rest);  // Output: [3, 4]
```

### **Object Destructuring:**

#### **Basic Syntax:**
```javascript
let person = { name: "Alice", age: 30 };
let { name, age } = person;
console.log(name, age);  // Output: Alice 30
```

#### **Renaming Variables:**
```javascript
let person = { name: "Alice", age: 30 };
let { name: personName, age: personAge } = person;
console.log(personName, personAge);  // Output: Alice 30
```

#### **Default Values:**
```javascript
let person = { name: "Alice" };
let { name, age = 25 } = person;
console.log(age);  // Output: 25
```

### **Real-World Scenario**: Destructuring is commonly used in JavaScript frameworks like React for handling props and state, allowing easy extraction of values from complex objects.

---

## 3. **Rest and Spread Operators**

### **Rest Operator (`...`)**

The rest operator is used to collect multiple elements into an array. It's commonly used in function parameters, array destructuring, and object destructuring.

#### **In Function Parameters:**
```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4));  // Output: 10
```

#### **In Object Destructuring:**
```javascript
let person = { name: "Alice", age: 30, city: "NY" };
let { name, ...rest } = person;
console.log(rest);  // Output: { age: 30, city: 'NY' }
```

### **Spread Operator (`...`)**

The spread operator is used to unpack elements from an array or object. It can be used in function calls, array literals, and object literals.

#### **In Arrays:**
```javascript
let arr1 = [1, 2];
let arr2 = [...arr1, 3, 4];
console.log(arr2);  // Output: [1, 2, 3, 4]
```

#### **In Objects:**
```javascript
let person = { name: "Alice", age: 30 };
let updatedPerson = { ...person, city: "NY" };
console.log(updatedPerson);  // Output: { name: "Alice", age: 30, city: "NY" }
```

### **Real-World Scenario**: These operators are used for tasks like combining arrays, merging object properties, and handling variable-length arguments in functions.

---

## 4. **JavaScript Callbacks**

**Definition**: A callback is a function passed into another function as an argument, which is then executed later, usually after some operation is complete.

### **Basic Example:**
```javascript
function greet(name, callback) {
  console.log(`Hello, ${name}`);
  callback();
}

function sayGoodbye() {
  console.log("Goodbye!");
}

greet("Alice", sayGoodbye);
// Output:
// Hello, Alice
// Goodbye!
```

**Real-World Scenario**: Callbacks are widely used in asynchronous operations like reading files, making HTTP requests, or handling user interactions.

---

## 5. **JavaScript Asynchronous Programming**

Asynchronous programming allows JavaScript to perform tasks like reading files or making HTTP requests without blocking the execution of other code.

### **Callbacks in Asynchronous Programming:**

```javascript
function fetchData(callback) {
  setTimeout(() => {
    callback("Data fetched");
  }, 2000);
}

fetchData(data => {
  console.log(data);  // Output: Data fetched (after 2 seconds)
});
```

### **Real-World Scenario**: Asynchronous programming is crucial in tasks like API calls, animations, or waiting for user input.

---

## 6. **JavaScript Promises**

**Definition**: A Promise is an object representing the eventual completion (or failure) of an asynchronous operation. It is a better way to handle asynchronous code compared to callbacks.

### **Basic Syntax:**
```javascript
let promise = new Promise((resolve, reject) => {
  let success = true;
  if (success) {
    resolve("Operation successful!");
  } else {
    reject("Operation failed.");
  }
});

promise
  .then(result => console.log(result))  // Output: Operation successful!
  .catch(error => console.log(error));
```

### **Chaining Promises:**
```javascript
let promise = new Promise((resolve, reject) => resolve("Step 1"))
  .then(result => {
    console.log(result);  // Output: Step 1
    return "Step 2";
  })
  .then(result => console.log(result))  // Output: Step 2
  .catch(error => console.log(error));
```

**Real-World Scenario**: Promises are used for handling API responses, loading resources, and chaining multiple asynchronous tasks.

---

## 7. **JavaScript Async/Await**

**Definition**: `async` and `await` make working with promises easier. `async` makes a function return a promise, and `await` pauses the execution of the function until the promise is resolved.

### **Basic Syntax:**
```javascript
async function fetchData() {
  let response = await fetch("https://api.example.com");
  let data = await response.json();
  console.log(data);
}

fetchData();
```

### **Real-World Scenario**: Async/await simplifies code that involves chaining multiple asynchronous actions, such as fetching data from APIs or handling file operations.

---

## 8. **Working with Fetch API**

**Definition**: The `fetch()` function is used to make network requests to retrieve or send data to a server asynchronously.

### **Basic Syntax:**
```javascript
fetch("https://api.example.com")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```

### **Using `async/await` with Fetch:**
```javascript
async function getData() {
  try {
    let response = await fetch("https://api.example.com");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}

getData();
```

**Real-World Scenario**: The `fetch()` API is essential for making AJAX calls to server-side applications or consuming RESTful APIs.

---

## 9. **Creating a Currency Converter Using Fetch API**

Now, let’s use the `fetch()` function to create a simple currency converter that fetches data from an API and converts amounts between two currencies.

### **Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Currency Converter</title>
</head>
<body>
  <h1>Currency Converter</h1>
  <input type="number" id="amount" placeholder="Enter amount">
  <select id="fromCurrency">
    <option value="USD">USD</option>
    <option value="EUR">EUR</option>
    <option value="INR">INR</option>
  </select>
  <select id="toCurrency">
    <option value="USD">USD</option>
    <option value="EUR">EUR</option>
    <option value="INR">INR</option>
  </select>
  <button id="convertButton">Convert</button>
  <h2 id="result"></h2>

  <script>
    document.getElementById("convertButton").addEventListener("click", convertCurrency);

    async function convertCurrency() {
      let amount = document.getElementById("amount").value;
      let fromCurrency = document.getElementById("fromCurrency").value;
      let toCurrency = document.getElementById("toCurrency").value;

      let url = `https://api.exchangerate-api.com/v4/latest/${fromCurrency}`;
      let response = await fetch(url);
      let data = await response.json();

      let conversionRate = data.rates[toCurrency];
      let convertedAmount = amount * conversionRate;

      document.getElementById("result").textContent = `Converted Amount: ${convertedAmount} ${toCurrency}`;
    }
  </script>
</body>
</html>
```

### **How it Works**:
1. The user enters an amount and selects the currencies they want to convert from and to.
2. The `fetch()` function retrieves the current exchange rates from the **ExchangeRate-API**.
3. The result is displayed dynamically based on the selected currencies.

---
