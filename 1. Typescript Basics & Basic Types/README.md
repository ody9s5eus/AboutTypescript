# 1. TypeScript Basics & Basic Types

tags: #TypeScript #Basics #Types  

TypeScript uses a syntax similar to JavaScript but adds a **static type system** to help write more reliable code.

---

## **1. Using Types**
In TypeScript, you can specify types for variables to enable **static type checking**.

```ts
let username: string = "Alice";  
let age: number = 25;  
let isAdmin: boolean = true;  
```
Here, `string`, `number`, and `boolean` are **basic types**.

---

## **2. TypeScript Types vs JavaScript Types**
JavaScript is **dynamically typed**, meaning variable types can change at runtime.

```js
let value = "Hello"; // Initially a string
value = 42; // No error, type changes to number
```

TypeScript, on the other hand, is **statically typed**, preventing unintended type changes.

```ts
let value: string = "Hello";
value = 42; // Error: Type 'number' is not assignable to type 'string'.
```
TypeScript helps catch type errors **before runtime**, improving maintainability.

---

## **3. Working with Number, String & Boolean**
The most fundamental types in TypeScript are `number`, `string`, and `boolean`.

### **📌 Number Type**
```ts
let price: number = 1000;
let tax: number = 0.1;
let total: number = price * (1 + tax);
```

### **📌 String Type**
```ts
let firstName: string = "John";
let greeting: string = `Hello, ${firstName}`;
```

### **📌 Boolean Type**
```ts
let isCompleted: boolean = false;
let isAvailable: boolean = true;
```

---

## **4. Type Assignment & Type Inference**
TypeScript allows both explicit type assignment and **type inference**.

### **📌 Explicit Type Assignment**
```ts
let count: number = 10;
let message: string = "Hello TypeScript";
```

### **📌 Type Inference**
TypeScript can infer types automatically.

```ts
let count = 10; // TypeScript infers 'number'
let message = "Hello TypeScript"; // TypeScript infers 'string'
```

---

## **5. Object Types**
You can define object types explicitly.

```ts
let person: { name: string; age: number } = {  
  name: "Alice",  
  age: 30  
};
```

Alternatively, you can use an **interface**.

```ts
interface Person {  
  name: string;  
  age: number;  
}

let user: Person = {  
  name: "Bob",  
  age: 25  
};
```

### **📌 Nested Object & Types**
Objects can contain other objects.

```ts
interface Address {
  city: string;
  country: string;
}

interface User {
  name: string;
  age: number;
  address: Address;
}

let user: User = {
  name: "Charlie",
  age: 28,
  address: {
    city: "Seoul",
    country: "Korea"
  }
};
```

---

## **6. Array Type**
You can define arrays like this:

```ts
let numbers: number[] = [1, 2, 3, 4, 5];
let names: string[] = ["Alice", "Bob", "Charlie"];
```

Alternatively, use a **generic array type**:

```ts
let numbers: Array<number> = [1, 2, 3, 4, 5];
```

---

## **7. Tuple**
A **tuple** is a fixed-length array with specified types.

```ts
let person: [string, number] = ["Alice", 30];
```

Tuples enforce strict typing and ordering.

---

## **8. Enum**
Enums define a set of named constants.

```ts
enum Color {
  Red,
  Green,
  Blue
}

let selectedColor: Color = Color.Green;
```

You can also manually assign values:

```ts
enum Status {
  Pending = "PENDING",
  Completed = "COMPLETED",
  Failed = "FAILED"
}

let orderStatus: Status = Status.Completed;
```

---

## **9. Any Type**
The `any` type allows variables to hold values of any type.

```ts
let value: any = "Hello";
value = 42; // No error
value = true; // No error
```

However, excessive use of `any` reduces TypeScript’s benefits.

---

## **10. Function Return Type & Void**
```ts
function sayHello(): void {
  console.log("Hello, TypeScript!");
}
```

---

## **11. Function Types & Callback**
```ts
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (x, y) => x + y;
```

---

## **12. The Unknown Type**
```ts
let unknownValue: unknown;
unknownValue = "Hello";
unknownValue = 42;
```

---

## **13. The Never Type**
```ts
function throwError(message: string): never {
  throw new Error(message);
}
```
