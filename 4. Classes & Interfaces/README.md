# Classes & Interfaces

tags: #TypeScript #Classes #Interfaces 

---

## **1. What are Classes?**
Classes are blueprints for creating objects with properties and methods.

```ts
class Car {
  brand: string;
  constructor(brand: string) {
    this.brand = brand;
  }
  drive() {
    console.log(`${this.brand} is driving.`);
  }
}
```

---

## **2. Creating a Class**

### **📌 Basic Class Structure**

```ts
class Person {
  name: string;
  constructor(name: string) {
    this.name = name;
  }
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}
const person = new Person("John");
person.greet();
```

---

## **3. Compiling to JavaScript**
TypeScript classes get compiled to JavaScript constructor functions.

```js
"use strict";
class Person {
  constructor(name) {
    this.name = name;
  }
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}
```

---

## **4. Constructor Functions & The `this` Key**
The `constructor` function initializes class properties, and `this` refers to the instance.

```ts
class Animal {
  species: string;
  constructor(species: string) {
    this.species = species;
  }
}
```

---

## **5. Public and Private Access Modifiers**
TypeScript allows restricting access using `public` and `private`.

```ts
class User {
  public username: string;
  private password: string;

  constructor(username: string, password: string) {
    this.username = username;
    this.password = password;
  }
}
```

---

## **6. Shorthand Initialization**
You can initialize and declare properties in the constructor shorthand.

```ts
class Employee {
  constructor(public name: string, private salary: number) {}
}
```

---

## **7. Readonly Properties**
Use `readonly` to prevent properties from being modified after initialization.

```ts
class Company {
  readonly name: string;
  constructor(name: string) {
    this.name = name;
  }
}
```

---

## **8. Inheritance**
Classes can inherit properties and methods from another class.

```ts
class Animal {
  constructor(public name: string) {}
}
class Dog extends Animal {
  bark() {
    console.log(`${this.name} is barking!`);
  }
}
```

---

## **9. Overriding Properties & The Protected Modifier**
The `protected` modifier allows access in subclasses.

```ts
class Parent {
  protected value: number = 10;
}
class Child extends Parent {
  showValue() {
    console.log(this.value);
  }
}
```

---

## **10. Getter & Setter**

```ts
class Person {
  private _age: number = 0;
  get age(): number {
    return this._age;
  }
  set age(value: number) {
    if (value >= 0) this._age = value;
  }
}
```

---

## **11. Static Methods & Properties**

```ts
class MathUtil {
  static PI: number = 3.14;
  static circleArea(radius: number): number {
    return this.PI * radius * radius;
  }
}
```

---

## **12. Abstract Classes**

```ts
abstract class Animal {
  abstract makeSound(): void;
}
class Dog extends Animal {
  makeSound() {
    console.log("Bark!");
  }
}
```

---

## **13. Singleton & Private Constructors**

```ts
class Singleton {
  private static instance: Singleton;
  private constructor() {}
  static getInstance() {
    if (!Singleton.instance) Singleton.instance = new Singleton();
    return Singleton.instance;
  }
}
```

---

## **14. Interface**
Interfaces define contracts for objects and classes.

```ts
interface Person {
  name: string;
  age: number;
}
```

---

## **15. Using Interface with Classes**

```ts
interface Animal {
  makeSound(): void;
}
class Dog implements Animal {
  makeSound() {
    console.log("Woof!");
  }
}
```

---

## **16. Why Interface?**
Interfaces provide strong type-checking and flexibility in object structures.

---

## **17. Readonly Interface Properties**

```ts
interface Car {
  readonly brand: string;
}
```

---

## **18. Extending Interfaces**

```ts
interface Animal {
  name: string;
}
interface Dog extends Animal {
  breed: string;
}
```

---

## **19. Interface as Function Types**

```ts
interface Greet {
  (name: string): string;
}
```

---

## **20. Optional Parameter & Properties**

```ts
interface User {
  name: string;
  age?: number;
}
```

---

## **21. Compiling Interface to JavaScript**
Interfaces are removed during compilation and only used for type-checking in TypeScript.
