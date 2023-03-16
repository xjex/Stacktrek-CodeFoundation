# [Data types](https://www.w3schools.com/js/js_datatypes.asp)

JavaScript has 8 data types

1. String
2. Number
3. Bigint
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object

### The Object Datatype
The object data type can contain:

1. An object
2. An array
3. A date

```
// Numbers:
let length = 16;
let weight = 7.5;

// Strings:
let color = "Yellow";
let lastName = "Johnson";

// Booleans
let x = true;
let y = false;

// Object:
const person = {firstName:"John", lastName:"Doe"};

// Array object:
const cars = ["Saab", "Volvo", "BMW"];

// Date object:
const date = new Date("2022-03-25");
```
------------------------------


String Manipulation in JavaScript
JavaScript provides several built-in methods for manipulating strings. Some of the most commonly used ones include:

1. Concatenation
To combine two or more strings in JavaScript, you can use the concatenation operator + or the concat() method.

javascript
Copy code
const str1 = 'Hello';
const str2 = 'World';
const result = str1 + ' ' + str2;
console.log(result); // Output: "Hello World"

const str3 = 'Goodbye';
const str4 = 'World';
const result2 = str3.concat(' ', str4);
console.log(result2); // Output: "Goodbye World"
2. Length
You can find the length of a string in JavaScript using the length property.

javascript
Copy code
const str = 'Hello World';
console.log(str.length); // Output: 11
3. Substring
To extract a portion of a string, you can use the substring() method.

javascript
Copy code
const str = 'Hello World';
const result = str.substring(0, 5);
console.log(result); // Output: "Hello"
4. Replace
To replace a substring with another substring in a string, you can use the replace() method.

javascript
Copy code
const str = 'Hello World';
const result = str.replace('World', 'Universe');
console.log(result); // Output: "Hello Universe"
5. Trim
To remove whitespace from the beginning and end of a string, you can use the trim() method.

javascript
Copy code
const str = '   Hello World   ';
const result = str.trim();
console.log(result); // Output: "Hello World"