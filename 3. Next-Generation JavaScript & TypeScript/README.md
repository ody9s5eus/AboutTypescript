# Next-Generation JavaScript & TypeScript

tags: #TypeScript #JavaScript #ES6 

---

## **1. let and const**

### **📌 Using `let` (Block Scoped Variables)**
The `let` keyword allows defining variables with block scope, replacing `var`.

```ts
let count = 10;
if (true) {
  let count = 20; // This count is scoped inside the block
  console.log(count); // 20
}
console.log(count); // 10
```

### **📌 Using `const` (Immutable Variables)**
The `const` keyword ensures that a variable cannot be reassigned after initialization.

```ts
const PI = 3.14;
// PI = 3.14159; // Error: Assignment to constant variable
```

---

## **2. Arrow Functions**

Arrow functions provide a concise way to define functions and preserve the `this` context.

```ts
const add = (a: number, b: number): number => a + b;
console.log(add(5, 10)); // 15
```

Arrow functions also inherit the `this` context from the surrounding scope:

```ts
class Person {
  name = "Alice";
  greet() {
    setTimeout(() => {
      console.log(`Hello, my name is ${this.name}`);
    }, 1000);
  }
}
const person = new Person();
person.greet();
```

---

## **3. Default Function Parameters**

Default parameters allow specifying default values if no argument is provided.

```ts
function greet(name: string = "Guest") {
  console.log(`Hello, ${name}!`);
}
greet(); // "Hello, Guest!"
greet("John"); // "Hello, John!"
```

---

## **4. Array & Object Destructuring**

### **📌 Array Destructuring**
Extract values from arrays conveniently:

```ts
const numbers = [10, 20, 30];
const [first, second] = numbers;
console.log(first, second); // 10 20
```

### **📌 Object Destructuring**
Extract properties from objects easily:

```ts
const user = { name: "Alice", age: 25 };
const { name, age } = user;
console.log(name, age); // Alice 25
```

---

## **5. How Code Gets Compiled**

TypeScript code is compiled to JavaScript before execution. You can control how TypeScript transpiles code using the `target` option in `tsconfig.json`.

Example:
```json
{
  "compilerOptions": {
    "target": "ES6"
  }
}
```

This ensures TypeScript compiles modern ES6+ features while maintaining compatibility with older JavaScript environments.

---

By leveraging modern JavaScript features, TypeScript provides a more robust development experience. 🚀
