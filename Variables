# Variables and Constants in JavaScript

## 1. Variables in JavaScript
Variables in JavaScript can be declared using `var`, `let`, or `const`.

### a. `let`
- Introduced in ES6.
- **Block-scoped**: Accessible only within the block it is declared.
- Can be updated but not re-declared in the same scope.

```javascript
let age = 25;
age = 30; // Allowed
console.log(age); // 30

{
    let age = 40; // Block-scoped
    console.log(age); // 40
}
console.log(age); // 30
```

---

### b. `const`
- Introduced in ES6.
- **Block-scoped** like `let`.
- **Cannot be updated or re-declared**.
- Requires initialization when declared.

```javascript
const birthYear = 1990;
// birthYear = 1995; // Error: Assignment to constant variable
console.log(birthYear); // 1990

{
    const birthYear = 2000; // Block-scoped
    console.log(birthYear); // 2000
}
console.log(birthYear); // 1990
```

- For objects or arrays, the reference cannot be changed, but the contents can.

```javascript
const person = { name: "Alice" };
person.name = "Bob"; // Allowed
console.log(person); // { name: "Bob" }

// person = { name: "Charlie" }; // Error: Assignment to constant variable
```

---

### c. `var`
- Available since the beginning of JavaScript.
- **Function-scoped**: Accessible throughout the function where it is declared.
- **Can be re-declared and updated** in the same scope.
- Avoid using `var` in modern JavaScript due to its quirks and issues.

```javascript
var message = "Hello";
message = "Hi"; // Allowed
console.log(message); // Hi

function greet() {
    var message = "Hello from inside";
    console.log(message); // Hello from inside
}
greet();
console.log(message); // Hi
```

---

## 2. Hoisting
- **Hoisting**: JavaScript moves declarations to the top of their scope during compile time.
- **Behavior**:
  - `var` is hoisted with an initial value of `undefined`.
  - `let` and `const` are hoisted but remain **uninitialized** until execution reaches their declaration.

### Example with `var` Hoisting

```javascript
console.log(greeting); // undefined
var greeting = "Hello, World!";
console.log(greeting); // Hello, World!
```

### Example with `let` and `const` Hoisting

```javascript
// console.log(name); // Error: Cannot access 'name' before initialization
let name = "Alice";

// console.log(age); // Error: Cannot access 'age' before initialization
const age = 30;
```

- **Temporal Dead Zone (TDZ)**: The time between entering the block and the actual declaration is when `let` and `const` cannot be accessed.

---

## 3. Examples with Combined Concepts

### Example 1: Block Scope with `let` and `const`

```javascript
{
    let x = 10;
    const y = 20;
    console.log(x, y); // 10 20
}
// console.log(x, y); // Error: x and y are not defined
```

### Example 2: Hoisting with `var`, `let`, and `const`

```javascript
function hoistingExample() {
    console.log(a); // undefined
    // console.log(b); // Error: Cannot access 'b' before initialization
    // console.log(c); // Error: Cannot access 'c' before initialization

    var a = 5;
    let b = 10;
    const c = 15;

    console.log(a, b, c); // 5 10 15
}
hoistingExample();
```

### Example 3: Mutable and Immutable `const`

```javascript
const colors = ["red", "blue"];
colors.push("green"); // Allowed: Modifying array contents
console.log(colors); // ["red", "blue", "green"]

// colors = ["yellow"]; // Error: Assignment to constant variable
```

### Example 4: Function Scope with `var`

```javascript
function testScope() {
    if (true) {
        var localVar = "I'm function-scoped!";
    }
    console.log(localVar); // Accessible here
}
testScope();
```

---

By using `let` and `const` effectively, you can write cleaner and more predictable code while avoiding many of the pitfalls associated with `var`.

