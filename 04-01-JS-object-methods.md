# **JavaScript Data Types and Their Methods**

## **1. String Data Type**

Strings in JavaScript are sequences of characters enclosed in single or double quotes (`'` or `"`). JavaScript provides numerous methods to manipulate strings, such as searching, replacing, and transforming text.

### **Common String Methods:**

1. **`charAt(index)`**  
   Returns the character at the specified index in a string.

   ```javascript
   let str = "Hello";
   console.log(str.charAt(1));  // Output: e
   ```

2. **`concat(string2, string3, ...)`**  
   Combines multiple strings into one.

   ```javascript
   let str1 = "Hello";
   let str2 = "World";
   console.log(str1.concat(" ", str2));  // Output: Hello World
   ```

3. **`includes(substring)`**  
   Checks if the string contains a specified substring.

   ```javascript
   let str = "Hello World";
   console.log(str.includes("World"));  // Output: true
   ```

4. **`indexOf(substring)`**  
   Returns the index of the first occurrence of the specified substring.

   ```javascript
   let str = "Hello World";
   console.log(str.indexOf("o"));  // Output: 4
   ```

5. **`lastIndexOf(substring)`**  
   Returns the index of the last occurrence of the specified substring.

   ```javascript
   let str = "Hello World";
   console.log(str.lastIndexOf("o"));  // Output: 7
   ```

6. **`match(regex)`**  
   Retrieves the result of matching a string against a regular expression.

   ```javascript
   let str = "The rain in Spain";
   console.log(str.match(/ain/));  // Output: ["ain"]
   ```

7. **`replace(search, replacement)`**  
   Replaces a specified substring with another substring.

   ```javascript
   let str = "Hello World";
   console.log(str.replace("World", "JavaScript"));  // Output: Hello JavaScript
   ```

8. **`search(regex)`**  
   Searches a string for a match to a regular expression and returns the position of the match.

   ```javascript
   let str = "Hello World";
   console.log(str.search("World"));  // Output: 6
   ```

9. **`slice(start, end)`**  
   Extracts a section of a string and returns a new string.

   ```javascript
   let str = "Hello World";
   console.log(str.slice(0, 5));  // Output: Hello
   ```

10. **`split(separator)`**  
    Splits a string into an array of substrings.

    ```javascript
    let str = "apple,banana,grape";
    console.log(str.split(","));  // Output: ["apple", "banana", "grape"]
    ```

11. **`startsWith(prefix)`**  
    Checks if a string starts with the specified prefix.

    ```javascript
    let str = "Hello World";
    console.log(str.startsWith("Hello"));  // Output: true
    ```

12. **`toLowerCase()`**  
    Converts a string to lowercase.

    ```javascript
    let str = "Hello World";
    console.log(str.toLowerCase());  // Output: hello world
    ```

13. **`toUpperCase()`**  
    Converts a string to uppercase.

    ```javascript
    let str = "Hello World";
    console.log(str.toUpperCase());  // Output: HELLO WORLD
    ```

14. **`trim()`**  
    Removes whitespace from both ends of a string.

    ```javascript
    let str = "  Hello World  ";
    console.log(str.trim());  // Output: Hello World
    ```

15. **`valueOf()`**  
    Returns the primitive value of a string.

    ```javascript
    let str = new String("Hello");
    console.log(str.valueOf());  // Output: Hello
    ```

---

## **2. Array Data Type**

Arrays are used to store ordered collections of data. JavaScript arrays come with numerous built-in methods to manipulate the array's elements.

### **Common Array Methods:**

1. **`push(element)`**  
   Adds one or more elements to the end of an array.

   ```javascript
   let arr = [1, 2];
   arr.push(3);
   console.log(arr);  // Output: [1, 2, 3]
   ```

2. **`pop()`**  
   Removes the last element from an array.

   ```javascript
   let arr = [1, 2, 3];
   arr.pop();
   console.log(arr);  // Output: [1, 2]
   ```

3. **`shift()`**  
   Removes the first element from an array.

   ```javascript
   let arr = [1, 2, 3];
   arr.shift();
   console.log(arr);  // Output: [2, 3]
   ```

4. **`unshift(element)`**  
   Adds one or more elements to the beginning of an array.

   ```javascript
   let arr = [2, 3];
   arr.unshift(1);
   console.log(arr);  // Output: [1, 2, 3]
   ```

5. **`concat(array2, array3, ...)`**  
   Merges two or more arrays into a new array.

   ```javascript
   let arr1 = [1, 2];
   let arr2 = [3, 4];
   console.log(arr1.concat(arr2));  // Output: [1, 2, 3, 4]
   ```

6. **`join(separator)`**  
   Joins all elements of an array into a string, separated by a specified separator.

   ```javascript
   let arr = [1, 2, 3];
   console.log(arr.join("-"));  // Output: 1-2-3
   ```

7. **`slice(start, end)`**  
   Returns a shallow copy of a portion of an array into a new array object.

   ```javascript
   let arr = [1, 2, 3, 4];
   console.log(arr.slice(1, 3));  // Output: [2, 3]
   ```

8. **`splice(start, deleteCount, item1, item2, ...)`**  
   Changes the contents of an array by removing or replacing elements.

   ```javascript
   let arr = [1, 2, 3, 4];
   arr.splice(2, 1, 5);
   console.log(arr);  // Output: [1, 2, 5, 4]
   ```

9. **`indexOf(element)`**  
   Returns the first index of the specified element, or `-1` if it's not found.

   ```javascript
   let arr = [1, 2, 3, 4];
   console.log(arr.indexOf(3));  // Output: 2
   ```

10. **`find(callback)`**  
    Returns the first element that satisfies the provided testing function.

    ```javascript
    let arr = [1, 2, 3, 4];
    let result = arr.find(x => x > 2);
    console.log(result);  // Output: 3
    ```

11. **`forEach(callback)`**  
    Executes a provided function once for each array element.

    ```javascript
    let arr = [1, 2, 3];
    arr.forEach(function(item) {
        console.log(item);  // Output: 1 2 3
    });
    ```

12. **`filter(callback)`**  
    Returns a new array with all elements that pass the test implemented by the provided function.

    ```javascript
    let arr = [1, 2, 3, 4];
    let filtered = arr.filter(x => x % 2 === 0);
    console.log(filtered);  // Output: [2, 4]
    ```

13. **`map(callback)`**  
    Creates a new array with the results of calling a provided function on every element.

    ```javascript
    let arr = [1, 2, 3];
    let doubled = arr.map(x => x * 2);
    console.log(doubled);  // Output: [2, 4, 6]
    ```

14. **`sort(compareFunction)`**  
    Sorts the elements of an array in place.

    ```javascript
    let arr = [3, 1, 2];
    arr.sort();
    console.log(arr);  // Output: [1, 2, 3]
    ```

15. **`reverse()`**  
    Reverses the order of elements in an array.

    ```javascript
    let arr = [1, 2, 3];
    arr.reverse();
    console.log(arr);  // Output: [3, 2, 1]
    ```

---

## **3. Number Data Type**

Numbers in JavaScript are used for performing arithmetic and represent both integers and floating-point numbers. Numbers have a few important methods that allow you to manipulate and format them.

### **Common Number Methods:**

1. **`toFixed(digits)`**  
   Formats a number using fixed-point notation.

   ```javascript
   let num = 5.12345;
   console.log(num.toFixed(2));  // Output: 5.12
   ```

2. **`toExponential(digits)`**  
   Returns a string representing the number in exponential notation.

   ```javascript
   let num = 12345;
   console.log(num.toExponential(2));  // Output: 1.23e+4
   ```

3. **`toPrecision(precision)`**  
   Formats a number to a specified precision.

   ```javascript
   let num = 5.12345;
   console.log(num.toPrecision(4));  // Output: 5.123
   ```

4. **`valueOf()`**  
   Returns the primitive value of a number.

   ```javascript
   let num = new Number(10);
   console.log(num.valueOf());  // Output: 10
   ```

5. **`isInteger()`**  
   Checks if a number is an integer.

   ```javascript
   let num = 10.5;
   console.log(Number.isInteger(num));  // Output: false
   ```

6. **`isFinite()`**  
   Checks if a value is a finite number.

   ```javascript
   let num = Infinity;
   console.log(Number.isFinite(num));  // Output: false
   ```

7. **`isNaN()`**  
   Checks if a value is `NaN` (Not-a-Number).

   ```javascript
   let num = NaN;
   console.log(Number.isNaN(num));  // Output: true
   ```

8. **`parseInt()`**  
   Parses a string and returns an integer.

   ```javascript
   let num = "123";
   console.log(parseInt(num));  // Output: 123
   ```

9. **`parseFloat()`**  
   Parses a string and returns a floating-point number.

   ```javascript
   let num = "10.25";
   console.log(parseFloat(num));  // Output: 10.25
   ```

10. **`toString()`**  
    Converts a number to a string.

    ```javascript
    let num = 123;
    console.log(num.toString());  // Output: "123"
    ```

11. **`toLocaleString()`**  
    Returns a string with a language-sensitive representation of a number.

    ```javascript
    let num = 123456.789;
    console.log(num.toLocaleString());  // Output: "123,456.789" (depends on locale)
    ```

12. **`Math.random()`**  
    Returns a random floating-point number between 0 and 1.

    ```javascript
    console.log(Math.random());  // Output: Random number between 0 and 1
    ```

13. **`Math.floor()`**  
    Rounds a number downward to the nearest integer.

    ```javascript
    console.log(Math.floor(2.9));  // Output: 2
    ```

14. **`Math.ceil()`**  
    Rounds a number upward to the nearest integer.

    ```javascript
    console.log(Math.ceil(2.1));  // Output: 3
    ```

15. **`Math.round()`**  
    Rounds a number to the nearest integer.

    ```javascript
    console.log(Math.round(2.5));  // Output: 3
    ```

---
