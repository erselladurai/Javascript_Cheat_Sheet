# JavaScript Functions: A Detailed Tutorial with Examples

Functions in JavaScript are reusable blocks of code designed to perform a specific task. Here's a comprehensive guide covering different types of functions and their usage.

---

## **1. Function Declaration**
A function declaration defines a named function that can be called anywhere in the scope.

### Example:
```javascript
function greet(name) {
  return `Hello, ${name}`;
}

console.log(greet("Alice")); // Output: Hello, Alice
```

---

## **2. Function Expression**
A function expression defines a function as part of an expression and is usually assigned to a variable. Unlike function declarations, function expressions are not hoisted.

### Example:
```javascript
const greet = function(name) {
  return `Hello, ${name}`;
};

console.log(greet("Bob")); // Output: Hello, Bob
```

---

## **3. Arrow Functions**
Arrow functions provide a concise way to write functions. They do not have their own `this` context.

### Example:
```javascript
const greet = (name) => `Hello, ${name}`;

console.log(greet("Charlie")); // Output: Hello, Charlie
```

---

## **4. Default Parameters**
Default parameters allow you to set default values for function arguments if no value is provided.

### Example:
```javascript
function multiply(a, b = 1) {
  return a * b;
}

console.log(multiply(5));    // Output: 5
console.log(multiply(5, 2)); // Output: 10
```

---

## **5. Higher-Order Functions**
Higher-order functions are functions that take other functions as arguments or return functions.

### Example:
```javascript
function processArray(arr, callback) {
  return arr.map(callback);
}

let doubled = processArray([1, 2, 3], (x) => x * 2);
console.log(doubled); // Output: [2, 4, 6]
```

---

## **6. Recursive Functions**
Recursive functions are functions that call themselves to solve smaller instances of a problem. Be sure to include a base case to avoid infinite recursion.

### Example:
```javascript
function factorial(n) {
  return n === 0 ? 1 : n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

---

## **Summary**
- **Function Declaration**: Defines a function with a name.
- **Function Expression**: Defines a function as part of an expression.
- **Arrow Functions**: Concise syntax for functions.
- **Default Parameters**: Set default values for parameters.
- **Higher-Order Functions**: Functions that take or return other functions.
- **Recursive Functions**: Solve problems by breaking them into smaller sub-problems.

Mastering these function types and techniques will make you a more effective JavaScript programmer!
