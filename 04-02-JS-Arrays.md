# JavaScript Arrays

## Introduction to Arrays
In JavaScript, an array is a data structure used to store multiple values in a single variable. Arrays can hold values of different types and are indexed starting from `0`. 

### Differences Between DSA Arrays and JavaScript Arrays

| **Aspect**               | **DSA Arrays** (General Concept)                  | **JavaScript Arrays** (Implementation)                                   |
|---------------------------|---------------------------------------------------|---------------------------------------------------------------------------|
| **Definition**            | A fixed-size, contiguous block of memory used to store elements of the same type. | A dynamic, high-level data structure that can hold elements of any type. |
| **Size**                  | Size is fixed at the time of creation (static).   | Dynamic; size can grow or shrink automatically.                          |
| **Data Types**            | All elements must be of the same type (e.g., integers, floats). | Can store mixed data types (e.g., numbers, strings, objects).            |
| **Memory Allocation**     | Uses contiguous memory blocks, ensuring fast access using an index. | Does not guarantee contiguous memory, as it is implemented as an object. |
| **Indexing**              | Fixed, integer-based, starting from `0`.         | Integer-based, starting from `0`, but `.at()` allows negative indexing.  |
| **Performance**           | Access time is `O(1)` for indexed retrieval, insertion/removal in the middle is costly. | Indexed retrieval is fast, but insertion/removal is slower due to dynamic resizing. |
| **Methods**               | Typically limited to manual implementations for insertion, deletion, traversal, etc. | Comes with built-in high-level methods like `.map()`, `.filter()`, `.reduce()`, etc. |
| **Type Checking**         | Strongly type-checked; all elements must conform to the specified type. | Weakly typed; can mix types freely within the same array.                |
| **Usage**                 | Used for low-level operations and performance-critical tasks. | Designed for flexibility and convenience in web development.             |
| **Negative Indexing**     | Not supported directly.                          | Supported using the `.at()` method.                                      |
| **Implementation**        | Found in low-level programming languages like C, C++, and Java. | A specialized implementation in JavaScript, built on objects.            |

---

### Key Features of DSA Arrays

1. **Static Memory**: Memory is pre-allocated at compile-time.
2. **Homogeneous Data**: Only one type of data is allowed in a single array.
3. **Fast Access**: Access to elements using indices is very fast due to contiguous memory allocation.
4. **Custom Operations**: Operations like sorting, searching, or resizing need to be implemented manually.

### Key Features of JavaScript Arrays

1. **Dynamic Size**: Arrays can grow or shrink in size automatically.
2. **Heterogeneous Data**: Allows storing different data types within the same array.
3. **Built-in Methods**: Offers high-level methods like `.map()`, `.filter()`, `.reduce()`, `.push()`, etc.
4. **Object-Like Behavior**: Can store sparse data and have properties.


### Syntax
```javascript
// Creating an array
let arrayName = [element1, element2, element3];
```

### Example
```javascript
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[0]); // Output: Apple
```

---

## Accessing Elements with Indexing

### Positive Indexing
Positive indexing is used to access elements starting from `0` (left-to-right).
```javascript
let arr = ["a", "b", "c"];
console.log(arr[0]); // Output: "a"
console.log(arr[2]); // Output: "c"
```

### Negative Indexing (Using `.at()`)
JavaScript introduced the `.at()` method in ES2022, which supports negative indexing. Negative indices count from the **end** of the array, with `-1` referring to the last element.

#### Differences Between `array[index]` and `array.at(index)`
1. **Negative Indexing**: Only `.at()` supports negative indices.
2. **Readability**: `.at()` can make your code more intuitive, especially when dealing with the end of arrays.

#### Examples:
```javascript
let arr = ["x", "y", "z"];

// Using bracket notation
console.log(arr[0]); // Output: "x"
// arr[-1] does not work as expected with bracket notation

// Using .at()
console.log(arr.at(0));  // Output: "x"
console.log(arr.at(-1)); // Output: "z" (last element)
```

---

## Types of Array Methods
Now let’s explore the methods and their use cases in detail.

---

### 1. **Adding and Removing Elements**
- **`push()`**: Adds elements to the end of the array.
- **`pop()`**: Removes the last element.
- **`unshift()`**: Adds elements to the beginning.
- **`shift()`**: Removes the first element.

#### Examples:
```javascript
let numbers = [1, 2, 3];

// push() and pop()
numbers.push(4);
console.log(numbers); // Output: [1, 2, 3, 4]
numbers.pop();
console.log(numbers); // Output: [1, 2, 3]

// unshift() and shift()
numbers.unshift(0);
console.log(numbers); // Output: [0, 1, 2, 3]
numbers.shift();
console.log(numbers); // Output: [1, 2, 3]
```

---

### 2. **Accessing and Finding Elements**
- **`indexOf()`**: Finds the index of the first occurrence of an element.
- **`includes()`**: Checks if an array contains a certain element.
- **`.at()`**: Access elements using positive or negative indices.

#### Examples:
```javascript
let colors = ["Red", "Blue", "Green"];

// indexOf()
console.log(colors.indexOf("Blue")); // Output: 1

// includes()
console.log(colors.includes("Green")); // Output: true

// .at() for negative indexing
console.log(colors.at(-1)); // Output: "Green" (last element)
```

---

### 3. **Transforming Arrays**
- **`map()`**: Creates a new array by applying a function to each element.
- **`filter()`**: Creates a new array with elements that pass a condition.

#### Examples:
```javascript
let numbers = [1, 2, 3, 4];

// map()
let squared = numbers.map(num => num ** 2);
console.log(squared); // Output: [1, 4, 9, 16]

// filter()
let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

---

### 4. **Combining and Slicing Arrays**
- **`concat()`**: Combines two or more arrays.
- **`slice()`**: Extracts a portion of an array (non-destructive).
- **`splice()`**: Adds/removes elements (destructive).

#### Examples:
```javascript
let arr1 = [1, 2];
let arr2 = [3, 4];

// concat()
let combined = arr1.concat(arr2);
console.log(combined); // Output: [1, 2, 3, 4]

// slice()
let sliced = combined.slice(1, 3);
console.log(sliced); // Output: [2, 3]

// splice()
combined.splice(1, 2, "a", "b");
console.log(combined); // Output: [1, "a", "b", 4]
```

---

### 5. **Sorting and Reversing**
- **`sort()`**: Sorts elements.
- **`reverse()`**: Reverses elements.

#### Examples:
```javascript
let names = ["John", "Alice", "Bob"];

// sort()
names.sort();
console.log(names); // Output: ["Alice", "Bob", "John"]

// reverse()
names.reverse();
console.log(names); // Output: ["John", "Bob", "Alice"]
```

---

### 6. **Iterating Through Arrays**
- **`forEach()`**: Iterates over array elements.
- **`reduce()`**: Reduces an array to a single value.

#### Examples:
```javascript
let numbers = [1, 2, 3, 4];

// forEach()
numbers.forEach(num => console.log(num));
// Output: 1, 2, 3, 4

// reduce()
let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // Output: 10
```

---

### 7. **Other Useful Methods**
- **`join()`**: Combines elements into a string.
- **`find()`**: Returns the first element that matches a condition.
- **`findIndex()`**: Returns the index of the first element that matches a condition.

#### Examples:
```javascript
let fruits = ["Apple", "Banana", "Cherry"];

// join()
let fruitString = fruits.join(", ");
console.log(fruitString); // Output: "Apple, Banana, Cherry"

// find()
let longName = fruits.find(fruit => fruit.length > 5);
console.log(longName); // Output: "Banana"

// findIndex()
let index = fruits.findIndex(fruit => fruit === "Cherry");
console.log(index); // Output: 2
```

---

## Examples of Iterators
Iterators allow you to traverse arrays systematically.

### Example 1: Using `entries()`
```javascript
let letters = ["a", "b", "c"];

for (let [index, letter] of letters.entries()) {
  console.log(`Index: ${index}, Letter: ${letter}`);
}
// Output:
// Index: 0, Letter: a
// Index: 1, Letter: b
// Index: 2, Letter: c
```

### Example 2: Using `keys()` and `values()`
```javascript
let numbers = [10, 20, 30];

// keys()
for (let key of numbers.keys()) {
  console.log(`Key: ${key}`);
}
// Output: Key: 0, Key: 1, Key: 2

// values()
for (let value of numbers.values()) {
  console.log(`Value: ${value}`);
}
// Output: Value: 10, Value: 20, Value: 30
```

---
