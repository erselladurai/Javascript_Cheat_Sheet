# JavaScript Higher-Order Functions Cheat Sheet

Higher-order functions are functions that take other functions as arguments or return functions. They are a key concept in functional programming and are widely used in JavaScript.

---

## **1. Definition**
A higher-order function is one that:
- Accepts other functions as arguments.
- Returns a function as its result.

### Syntax Example:
```javascript
function higherOrderFunction(callback) {
  return callback();
}
```

---

## **2. Common Examples of Higher-Order Functions**

### **a. `map`**
Creates a new array by applying a function to each element of an array.

#### Syntax:
```javascript
array.map(callback(currentValue, index, array))
```

#### Example:
```javascript
const numbers = [1, 2, 3];
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // Output: [2, 4, 6]
```

---

### **b. `filter`**
Creates a new array containing elements that pass a specified test.

#### Syntax:
```javascript
array.filter(callback(currentValue, index, array))
```

#### Example:
```javascript
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter((num) => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

---

### **c. `reduce`**
Applies a function to reduce the array to a single value.

#### Syntax:
```javascript
array.reduce(callback(accumulator, currentValue, index, array), initialValue)
```

#### Example:
```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // Output: 10
```

---

### **d. `forEach`**
Executes a provided function once for each array element.

#### Syntax:
```javascript
array.forEach(callback(currentValue, index, array))
```

#### Example:
```javascript
const numbers = [1, 2, 3];
numbers.forEach((num) => console.log(num));
// Output:
// 1
// 2
// 3
```

---

### **e. `find`**
Returns the first element that satisfies the condition.

#### Syntax:
```javascript
array.find(callback(currentValue, index, array))
```

#### Example:
```javascript
const numbers = [1, 2, 3, 4];
const firstEven = numbers.find((num) => num % 2 === 0);
console.log(firstEven); // Output: 2
```

---

### **f. `some`**
Tests whether at least one element passes the condition.

#### Syntax:
```javascript
array.some(callback(currentValue, index, array))
```

#### Example:
```javascript
const numbers = [1, 2, 3, 4];
const hasEven = numbers.some((num) => num % 2 === 0);
console.log(hasEven); // Output: true
```

---

### **g. `every`**
Tests whether all elements pass the condition.

#### Syntax:
```javascript
array.every(callback(currentValue, index, array))
```

#### Example:
```javascript
const numbers = [2, 4, 6];
const allEven = numbers.every((num) => num % 2 === 0);
console.log(allEven); // Output: true
```

---

### **h. `flatMap`**
Combines the `map` and `flat` methods into a single method.

#### Syntax:
```javascript
array.flatMap(callback(currentValue, index, array))
```

#### Example:
```javascript
const arr = [1, 2, [3, 4]];
const flattened = arr.flatMap((num) => (Array.isArray(num) ? num : [num]));
console.log(flattened); // Output: [1, 2, 3, 4]
```

---

### **i. `sort`**
Sorts the elements of an array in place.

#### Syntax:
```javascript
array.sort(compareFunction(a, b))
```

#### Example:
```javascript
const names = ["Charlie", "Alice", "Bob"];
const sorted = names.sort((a, b) => a.localeCompare(b));
console.log(sorted); // Output: ["Alice", "Bob", "Charlie"]
```

---

### **j. Custom Higher-Order Function**
You can create your own higher-order functions.

#### Example:
```javascript
function processArray(arr, callback) {
  return arr.map(callback);
}

const numbers = [1, 2, 3];
const squared = processArray(numbers, (num) => num ** 2);
console.log(squared); // Output: [1, 4, 9]
```

---

## **3. Practical Applications of Higher-Order Functions**

### **a. Sorting an Array**
```javascript
const names = ["Alice", "Bob", "Charlie"];
const sortedNames = names.sort((a, b) => a.localeCompare(b));
console.log(sortedNames); // Output: ["Alice", "Bob", "Charlie"]
```

### **b. Chaining Methods**
```javascript
const numbers = [1, 2, 3, 4];
const result = numbers
  .filter((num) => num % 2 === 0) // Filter even numbers
  .map((num) => num * 2);         // Double the values

console.log(result); // Output: [4, 8]
```

### **c. Event Listeners**
Higher-order functions are frequently used in event handling.
```javascript
document.getElementById("btn").addEventListener("click", () => {
  console.log("Button clicked!");
});
```

---

## **Summary**
- **Higher-order functions** make code more readable and modular.
- They are widely used in functional programming and JavaScript libraries like Lodash, React, and RxJS.
- Mastering them is essential for writing clean and efficient JavaScript code.
