# Advanced JavaScript: Modern JavaScript and Asynchronous Programming
  ### Go back to [JavaScript Tutorial](README.md)
---

## Table of Contents

- [Promises](#promises)
- [Callback Functions](#callback-functions)
- [Async/Await](#asyncawait)
- [Asynchronous Programming in JavaScript](#asynchronous-programming-in-javascript)
- [Working with Fetch API](#working-with-fetch-api)
- [Real-world Example: Currency Converter API](#real-world-example-currency-converter-api)

---

## Promises

### What is a Promise?

A **Promise** is a placeholder for a value that will be available at some point in the future. It represents the eventual result of an asynchronous operation. Promises are used to handle asynchronous operations like API calls, file reading, and other tasks that take time.

A Promise has three states:
1. **Pending**: The promise is still being executed.
2. **Resolved**: The operation is successful, and the promise is completed.
3. **Rejected**: The operation failed, and the promise is rejected.

### Example:

```javascript
let myPromise = new Promise((resolve, reject) => {
  let success = true;  // This can be determined based on some condition

  if (success) {
    resolve("Operation was successful");
  } else {
    reject("Operation failed");
  }
});

myPromise
  .then((message) => {
    console.log(message); // Will be called if the promise is resolved
  })
  .catch((error) => {
    console.log(error); // Will be called if the promise is rejected
  });
```

### Explanation:
- **resolve(value)**: If the promise is successful, it calls the `resolve` function with a value.
- **reject(error)**: If the promise fails, it calls the `reject` function with an error message.

### Real-World Scenario:
A real-world scenario might involve an API call to fetch user data. The data will only be available after the request finishes. We use a promise to represent this pending operation.

---

## Callback Functions

### What is a Callback?

A **callback** function is a function that is passed as an argument to another function and is executed after the completion of the main function. In JavaScript, callbacks are used to handle asynchronous operations.

### Example:

```javascript
function fetchData(callback) {
  setTimeout(() => {
    let data = "Data from server";
    callback(data);
  }, 2000);
}

function processData(data) {
  console.log("Processed: " + data);
}

fetchData(processData);
```

### Explanation:
- The `fetchData` function simulates a delay (using `setTimeout`) and calls the `callback` function once the data is "fetched."
- The `processData` function is passed as a callback to `fetchData` and is called once the data is retrieved.

### Callback Hell:
While callbacks are useful, they can lead to "callback hell" (or "pyramid of doom") when you have multiple nested callbacks. This makes the code hard to read and maintain.

Example of Callback Hell:

```javascript
fetchData(function(data) {
  fetchData(function(data) {
    fetchData(function(data) {
      // Deep nesting makes it hard to follow
    });
  });
});
```

---

## Async/Await

### What is Async/Await?

`async` and `await` are used to simplify working with Promises in asynchronous code. 

- **async**: Declares an asynchronous function that implicitly returns a Promise.
- **await**: Pauses the execution of the async function until the Promise is resolved or rejected.

### Example:

```javascript
async function fetchUserData() {
  let userData = await fetch("https://jsonplaceholder.typicode.com/users");
  let data = await userData.json(); // Resolves the response
  console.log(data);
}

fetchUserData();
```

### Explanation:
- The `fetchUserData` function is declared as `async`, which allows us to use `await` inside it.
- The `await` keyword pauses execution until the `fetch` Promise is resolved and then processes the result (`.json()` method).

### Benefits of Async/Await:
- **More readable**: Avoids deeply nested callback functions.
- **Error handling**: Works seamlessly with `try/catch` for error handling.

### Real-World Scenario:
Fetching data from an API endpoint and processing the response can be done in a simple, readable manner using async/await. It allows you to write asynchronous code as though it were synchronous.

---

## Asynchronous Programming in JavaScript

### Why Asynchronous Programming?

Asynchronous programming allows JavaScript to perform non-blocking operations. Instead of waiting for an operation to complete (like reading a file or making an API call), JavaScript can continue executing other tasks while waiting for the operation to finish.

### Event Loop:

JavaScript operates on a **single-threaded** event loop, which means it executes one operation at a time. However, it doesn't wait for long-running tasks (like HTTP requests or timers) to complete. Instead, it places them in the **event queue** and processes them later once the main thread is free.

### Example: Asynchronous Code Execution

```javascript
console.log("Start");

setTimeout(() => {
  console.log("Inside setTimeout");
}, 1000);

console.log("End");
```

### Output:

```
Start
End
Inside setTimeout
```

### Explanation:
- Even though `setTimeout` is a time-consuming operation, the event loop allows "Start" and "End" to be printed immediately. The callback function inside `setTimeout` is placed in the event queue and executed after the main thread completes.

---

## Working with Fetch API

### What is the Fetch API?

The **Fetch API** allows you to make network requests to fetch data from external sources. It returns a Promise, which can be used to handle the response asynchronously.

### Example:

```javascript
async function fetchData() {
  let response = await fetch("https://jsonplaceholder.typicode.com/posts");
  let posts = await response.json();
  console.log(posts);
}

fetchData();
```

### Explanation:
- The `fetch` function is used to make an HTTP GET request to the given URL.
- The `response.json()` method converts the response into a JSON format, which can be used in JavaScript.

### Real-World Scenario:
You might use the Fetch API to get a list of users from a server, display them in a table, and then let users click on a user to view their details.

---

## Real-World Example: Currency Converter API

### Using the Fetch API to Create a Currency Converter

In this example, we'll create a currency converter that fetches exchange rates using an external API.

### Example:

```javascript
async function getExchangeRate(baseCurrency, targetCurrency) {
  let response = await fetch(`https://api.exchangerate-api.com/v4/latest/${baseCurrency}`);
  let data = await response.json();
  let rate = data.rates[targetCurrency];
  return rate;
}

async function convertCurrency(amount, baseCurrency, targetCurrency) {
  let rate = await getExchangeRate(baseCurrency, targetCurrency);
  let convertedAmount = amount * rate;
  console.log(`Converted amount: ${convertedAmount} ${targetCurrency}`);
}

convertCurrency(100, "USD", "EUR");
```

### Explanation:
1. The `getExchangeRate` function fetches the latest exchange rates for a given base currency (like USD) and returns the rate for the target currency (like EUR).
2. The `convertCurrency` function calculates the converted amount by multiplying the input amount by the exchange rate.
3. The result is displayed in the console.

---
