**JavaScript Programming Cheat Sheet**

### **Table of Contents**

1. Variables and Constants
2. Data Types
3. Operators
4. Control Flow
5. Functions
6. Arrays
7. Objects
8. Advanced Array and Object Operations
9. Error Handling
10. Closures
11. Prototypes and Inheritance
12. Classes
13. Modules
14. Promises and Async/Await
15. Regular Expressions
16. Advanced Topics

---

### **1. Variables and Constants**

- **Declaring Variables**:

```javascript
let variable = "Changeable"; // Block scope
const constant = "Unchangeable"; // Block scope
var globalVariable = "Old syntax"; // Function scope
```

- **Hoisting**: Variables declared with `var` are hoisted with `undefined` as their initial value. `let` and `const` are hoisted but uninitialized.

---

### **2. Data Types**

- **Primitive Types**:

  - Number: `let num = 42;`
  - String: `let str = "Hello!";`
  - Boolean: `let isTrue = true;`
  - Undefined: `let x;`
  - Null: `let emptyValue = null;`
  - Symbol: `let sym = Symbol("unique");`
  - BigInt: `let bigInt = 9007199254740991n;`

- **Reference Types**:

  - Objects: `let obj = { name: "Alice" };`
  - Arrays: `let arr = [1, 2, 3];`
  - Functions: `function myFunc() {}`

---

### **3. Operators**

- **Arithmetic**: `+`, `-`, `*`, `/`, `%`, `**`.

```javascript
let sum = 5 + 3;
let power = 2 ** 3; // 8
```

- **Comparison**: `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`.
- **Logical**: `&&`, `||`, `!`.
- **Bitwise**: `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`.
- **Ternary**: `condition ? value1 : value2`.

```javascript
let isAdult = age >= 18 ? "Yes" : "No";
```

- **Spread and Rest**:

```javascript
let arr = [1, 2, 3];
let expanded = [...arr, 4, 5];
function sum(...args) {
  return args.reduce((a, b) => a + b);
}
```

---

### **4. Control Flow**

- **If-Else Statements**:

```javascript
if (condition) {
  // Code
} else if (anotherCondition) {
  // Code
} else {
  // Code
}
```

- **Switch**:

```javascript
switch (key) {
  case value:
    // Code
    break;
  default:
    // Fallback code
}
```

- **Loops**:
  - For: `for (let i = 0; i < 5; i++) {}`
  - While: `while (condition) {}`
  - Do-While: `do {} while (condition);`

---

### **5. Functions**

- **Function Declaration**:

```javascript
function greet(name) {
  return `Hello, ${name}`;
}
```

- **Function Expression**:

```javascript
const greet = function(name) {
  return `Hello, ${name}`;
};
```

- **Arrow Functions**:

```javascript
const greet = (name) => `Hello, ${name}`;
```

- **Default Parameters**:

```javascript
function multiply(a, b = 1) {
  return a * b;
}
```

- **Higher-Order Functions**: Functions that take other functions as arguments or return functions.

```javascript
function processArray(arr, callback) {
  return arr.map(callback);
}
let doubled = processArray([1, 2, 3], (x) => x * 2);
```

- **Recursive Functions**:

```javascript
function factorial(n) {
  return n === 0 ? 1 : n * factorial(n - 1);
}
```

---

### **7. Objects**

- **Object Basics**:

```javascript
let person = {
  name: "Alice",
  age: 25,
  greet() {
    console.log("Hi, I'm Alice.");
  }
};
```

- **Accessing Properties**:

```javascript
console.log(person.name); // Dot notation
console.log(person["age"]); // Bracket notation
```

- **Adding/Deleting Properties**:

```javascript
person.job = "Developer";
delete person.age;
```

- **Object Methods**: `Object.keys()`, `Object.values()`, `Object.entries()`.

- **Object Copying**:

```javascript
let copiedPerson = { ...person }; // Shallow copy
```

---

### **11. Prototypes and Inheritance**

- **Prototype Basics**:

```javascript
function Person(name) {
  this.name = name;
}
Person.prototype.greet = function() {
  console.log(`Hi, I'm ${this.name}`);
};
```

- **Inheritance**:

```javascript
function Developer(name, skills) {
  Person.call(this, name);
  this.skills = skills;
}
Developer.prototype = Object.create(Person.prototype);
```

- **Prototype Chain**: Understanding the hierarchy of object lookups.

```javascript
console.log(Object.getPrototypeOf(new Developer()));
```

---

### **12. Classes**

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}
class Developer extends Person {
  constructor(name, age, skills) {
    super(name, age);
    this.skills = skills;
  }
}
```

- **Static Methods**: Methods that belong to the class, not the instance.

```javascript
class Utility {
  static log(message) {
    console.log(message);
  }
}
Utility.log("Static method call");
```

- **Private Fields**:

```javascript
class Counter {
  #count = 0;
  increment() {
    this.#count++;
  }
}
```

---

### **13. Modules**

- **Exporting**:

```javascript
export const greet = () => "Hello!";
```

- **Importing**:

```javascript
import { greet } from "./module.js";
console.log(greet());
```

- **Dynamic Imports**:

```javascript
import("./module.js").then((module) => {
  module.greet();
});
```

---

### **15. Regular Expressions**

- **Syntax**:

```javascript
let regex = /pattern/;
let result = regex.test("test string");
```

- **Common Patterns**:

  - Digits: `/\d+/`
  - Word Characters: `/\w+/`
  - Repeating Patterns: `/a{2,4}/`

- **Match and Replace**:

```javascript
let str = "Hello World!";
let replaced = str.replace(/World/, "JavaScript");
```

---

### **16. Advanced Topics**

- **Memoization**: Caching results of expensive function calls.

```javascript
function memoize(fn) {
  const cache = {};
  return (...args) => {
    const key = JSON.stringify(args);
    if (!cache[key]) {
      cache[key] = fn(...args);
    }
    return cache[key];
  };
}
```

- **Currying**:

```javascript
const add = (a) => (b) => a + b;
console.log(add(2)(3)); // 5
```

- **Generators**:

```javascript
function* generator() {
  yield 1;
  yield 2;
}
const gen = generator();
console.log(gen.next().value); // 1
```

- **WeakMap and WeakSet**:

```javascript
let weakMap = new WeakMap();
let obj = {};
weakMap.set(obj, "value");
```

---

This cheat sheet provides a robust summary of JavaScript programming concepts. Let me know if you need further expansions or customizations!

