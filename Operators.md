# JavaScript Operators

JavaScript provides a variety of operators to perform different tasks like arithmetic, comparisons, logical operations, and more. Here's a comprehensive guide.

---

## 1. Arithmetic Operators

Arithmetic operators are used to perform mathematical operations.

### Examples:
```javascript
let a = 10;
let b = 3;

let sum = a + b;     // Addition: 10 + 3 = 13
let diff = a - b;    // Subtraction: 10 - 3 = 7
let product = a * b; // Multiplication: 10 * 3 = 30
let quotient = a / b; // Division: 10 / 3 = 3.33
let remainder = a % b; // Modulus: 10 % 3 = 1
let power = a ** b;  // Exponentiation: 10^3 = 1000
```

---

## 2. Comparison Operators

Comparison operators are used to compare two values and return a boolean (`true` or `false`).

### Examples:
```javascript
let x = 5;
let y = "5";

console.log(x == y);  // true: Equal (loose comparison)
console.log(x === y); // false: Strict equal (checks type too)
console.log(x != y);  // false: Not equal (loose comparison)
console.log(x !== y); // true: Strict not equal
console.log(x > 3);   // true: Greater than
console.log(x < 3);   // false: Less than
console.log(x >= 5);  // true: Greater than or equal to
console.log(x <= 5);  // true: Less than or equal to
```

---

## 3. Logical Operators

Logical operators are used to combine or invert boolean values.

### Examples:
```javascript
let isAdult = true;
let hasLicense = false;

console.log(isAdult && hasLicense); // false: AND operator
console.log(isAdult || hasLicense); // true: OR operator
console.log(!isAdult);              // false: NOT operator
```

---

## 4. Bitwise Operators

Bitwise operators work on binary representations of numbers.

### Examples:
```javascript
let m = 5; // Binary: 0101
let n = 3; // Binary: 0011

console.log(m & n);  // 1: AND
console.log(m | n);  // 7: OR
console.log(m ^ n);  // 6: XOR
console.log(~m);     // -6: NOT
console.log(m << 1); // 10: Left shift
console.log(m >> 1); // 2: Right shift
console.log(m >>> 1);// 2: Unsigned right shift
```

---

## 5. Ternary Operator

The ternary operator provides a shorthand way to write conditional statements.

### Examples:
```javascript
let age = 20;

let isAdult = age >= 18 ? "Yes" : "No"; 
console.log(isAdult); // "Yes"
```

---

## 6. Spread and Rest Operators

### **Spread Operator (`...`)**
The spread operator is used to expand arrays or objects into individual elements or properties.

### Examples:
```javascript
let arr = [1, 2, 3];
let expanded = [...arr, 4, 5];
console.log(expanded); // [1, 2, 3, 4, 5]

let obj1 = { name: "Alice" };
let obj2 = { age: 25 };
let merged = { ...obj1, ...obj2 };
console.log(merged); // { name: "Alice", age: 25 }
```

---

### **Rest Operator (`...`)**
The rest operator collects multiple elements into a single array-like parameter.

### Examples:
```javascript
function sum(...args) {
  return args.reduce((a, b) => a + b);
}

console.log(sum(1, 2, 3, 4)); // 10

function greet(greeting, ...names) {
  return `${greeting}, ${names.join(", ")}`;
}

console.log(greet("Hello", "Alice", "Bob", "Charlie")); // "Hello, Alice, Bob, Charlie"
```

---

### Another Example
```javascript
function display(name, ...args) {
   console.log(`${name}, ${args.join(",")}`);
}

display("Selladurai", "kajhs", "askasd", "asdiaui");
```

### Output:
```
Selladurai, kajhs, askasd, asdiaui
