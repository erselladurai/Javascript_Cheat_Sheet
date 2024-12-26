# JavaScript Mocha and Chai Cheat Sheet Tutorial

## 1. Setting Up Mocha and Chai

### Install Mocha and Chai
```bash
npm install --save-dev mocha chai
```

### Add a Test Script in `package.json`
```json
"scripts": {
  "test": "mocha"
}
```

### Directory Structure
```
├── test/
│   └── example.test.js
└── src/
    └── app.js
```

---

## 2. Mocha Basics

### a) Describe and It Blocks
- `describe`: Groups related tests.
- `it`: Defines a single test.
```javascript
describe('Array', function () {
  it('should return -1 when value is not present', function () {
    assert.equal([1, 2, 3].indexOf(4), -1);
  });
});
```

### b) Hooks in Mocha
- `before()`: Runs once before the tests in a block.
- `after()`: Runs once after the tests in a block.
- `beforeEach()`: Runs before each test in a block.
- `afterEach()`: Runs after each test in a block.

```javascript
describe('Hooks Example', function () {
  before(function () {
    console.log('Run before all tests');
  });

  after(function () {
    console.log('Run after all tests');
  });

  beforeEach(function () {
    console.log('Run before each test');
  });

  afterEach(function () {
    console.log('Run after each test');
  });

  it('Example Test 1', function () {
    console.log('Test 1');
  });

  it('Example Test 2', function () {
    console.log('Test 2');
  });
});
```

---

## 3. Chai Assertions

### Types of Assertions
1. **Assert Style**:
```javascript
const assert = require('chai').assert;
assert.equal(4, 4, '4 equals 4');
assert.isTrue(true, 'is true');
assert.isFalse(false, 'is false');
assert.deepEqual({ a: 1 }, { a: 1 }, 'objects are deeply equal');
assert.typeOf('hello', 'string', 'is a string');
assert.lengthOf([1, 2, 3], 3, 'array has length of 3');
```

2. **Expect Style**:
```javascript
const expect = require('chai').expect;
expect(4).to.equal(4);
expect('hello').to.be.a('string');
expect([1, 2, 3]).to.have.lengthOf(3);
expect({ a: 1 }).to.deep.equal({ a: 1 });
expect(false).to.be.false;
```

3. **Should Style**:
```javascript
const should = require('chai').should();
(4).should.equal(4);
'hello'.should.be.a('string');
false.should.be.false;
[1, 2, 3].should.have.lengthOf(3);
({ a: 1 }).should.deep.equal({ a: 1 });
```

---

## 4. Testing Asynchronous Code

### Using Callbacks
```javascript
describe('Async Callback Test', function () {
  it('should complete async operation', function (done) {
    setTimeout(function () {
      assert.isTrue(true);
      done();
    }, 1000);
  });
});
```

### Using Promises
```javascript
describe('Async Promise Test', function () {
  it('should resolve the promise', function () {
    return new Promise((resolve) => {
      setTimeout(() => {
        assert.isTrue(true);
        resolve();
      }, 1000);
    });
  });
});
```

### Using Async/Await
```javascript
describe('Async/Await Test', function () {
  it('should handle async/await', async function () {
    const result = await new Promise((resolve) => {
      setTimeout(() => resolve(true), 1000);
    });
    assert.isTrue(result);
  });
});
```

---

## 5. Handling Test Failures

### Assertions Throwing Errors
```javascript
it('should fail when assertion is false', function () {
  assert.equal(1, 2, '1 does not equal 2');
});
```

### Retry Mechanism
```javascript
describe('Retries Example', function () {
  this.retries(3);

  it('should pass after a few attempts', function () {
    const random = Math.random();
    assert.isTrue(random > 0.5);
  });
});
```

---

## 6. Running Mocha Tests

### Run Tests
```bash
npm test
```

### Run a Specific Test File
```bash
npx mocha test/example.test.js
```

### Run Tests with Options
```bash
npx mocha --reporter spec --timeout 5000
```

---

## 7. Chai Plugins

### chai-as-promised
Install:
```bash
npm install chai-as-promised
```
Usage:
```javascript
const chai = require('chai');
const chaiAsPromised = require('chai-as-promised');
chai.use(chaiAsPromised);
const expect = chai.expect;

it('should resolve the promise', function () {
  return expect(Promise.resolve('done')).to.eventually.equal('done');
});
```

---

## 8. Advanced Mocha Features

### Parallel Testing
Run tests in parallel to speed up execution:
```bash
npx mocha --parallel
```

### Custom Reporters
Use built-in or custom reporters to format test results:
```bash
npx mocha --reporter spec
npx mocha --reporter json
```

### Dynamic Test Generation
```javascript
[1, 2, 3].forEach((num) => {
  it(`should work for ${num}`, function () {
    assert.isTrue(num > 0);
  });
});
```

---

## 9. Additional Chai Techniques

### Deep Equality
```javascript
const obj1 = { name: 'test' };
const obj2 = { name: 'test' };
expect(obj1).to.deep.equal(obj2);
```

### Nested Property Assertions
```javascript
const obj = { nested: { key: 'value' } };
expect(obj).to.have.nested.property('nested.key', 'value');
```

### Length Assertions
```javascript
expect([1, 2, 3]).to.have.lengthOf(3);
```

### Key Inclusion
```javascript
const obj = { name: 'test' };
expect(obj).to.include.keys('name');
```

### String Inclusion
```javascript
expect('hello world').to.include('hello');
```

### Array Members
```javascript
expect([1, 2, 3]).to.have.members([3, 2, 1]);
```

### Change Assertions
```javascript
let value = 0;
function increment() {
  value += 1;
}
expect(increment).to.change(() => value);
```

### Increase/Decrease Assertions
```javascript
let count = 5;
function add() {
  count++;
}
expect(add).to.increase(() => count);
```

### Match Assertions
```javascript
expect('foobar').to.match(/^foo/);
```

### Satisfy Assertions
```javascript
expect(2).to.satisfy((num) => num > 0 && num < 5);
```

---

## 10. Integrating with CI/CD

### Running Tests in CI
Add the following to your CI/CD pipeline:
```bash
npm install
npm test
```

### Generating Test Coverage
Install and use `nyc`:
```bash
npm install --save-dev nyc
npx nyc mocha
```

---

## 11. Mocking and Stubbing with Sinon.js

### Install Sinon
```bash
npm install --save-dev sinon
```

### Example: Stubbing a Function
```javascript
const sinon = require('sinon');
const myObj = { method: () => 'real' };

sinon.stub(myObj, 'method').returns('stubbed');
assert.equal(myObj.method(), 'stubbed');
```

---

This cheat sheet has been expanded to cover advanced features, assertions, techniques, and CI/CD integration. Use it as a comprehensive guide for mastering Mocha and Chai!

