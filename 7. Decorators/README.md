# Decorators

tags: #TypeScript #Decorators  

---

## **1. Class Decorator**
Class decorators allow modifying a class behavior.

```ts
function Logger(constructor: Function) {
  console.log("Logging class...");
}
@Logger
class Person {
  name = "John";
  constructor() {
    console.log("Creating Person...");
  }
}
```

---

## **2. Working with Decorator Factories**
Decorator factories allow passing arguments to decorators.

```ts
function Logger(logMessage: string) {
  return function (constructor: Function) {
    console.log(logMessage);
  };
}
@Logger("Logging Person Class")
class Person {}
```

---

## **3. Building More Useful Decorators**
Decorators can be used to store metadata.

```ts
function WithTemplate(template: string, hookId: string) {
  return function<T extends { new (...args: any[]): { name: string } }>(
    originalConstructor: T
  ) {
    return class extends originalConstructor {
      constructor(...args: any[]) {
        super(...args);
        const hookEl = document.getElementById(hookId);
        if (hookEl) {
          hookEl.innerHTML = template;
          hookEl.querySelector("h1")!.textContent = this.name;
        }
      }
    };
  };
}
@WithTemplate("<h1>My Person</h1>", "app")
class Person {
  name = "John";
  constructor() {
    console.log("Creating Person...");
  }
}
```

---

## **4. Diving into Property Decorators**
Property decorators allow modifying properties.

```ts
function Log(target: any, propertyName: string | Symbol) {
  console.log("Property decorator called!", target, propertyName);
}
class Product {
  @Log
  title: string;
  constructor(title: string) {
    this.title = title;
  }
}
```

---

## **5. Accessors & Parameter Decorators**
Decorators can also be applied to accessors and parameters.

```ts
function LogAccessor(target: any, name: string, descriptor: PropertyDescriptor) {
  console.log("Accessor decorator!");
}
class Product {
  private _price: number;
  constructor(price: number) {
    this._price = price;
  }
  @LogAccessor
  set price(value: number) {
    if (value > 0) {
      this._price = value;
    }
  }
}
```

---

## **6. When Do Decorators Execute?**
Decorators execute when the class is defined, not when instantiated.

---

## **7. Returning and Changing a Class in Class Decorator**
Decorators can return a modified class.

```ts
function Logger(constructor: Function) {
  return class extends constructor {
    newProperty = "New Value";
  };
}
@Logger
class Person {}
```

---

## **8. Other Decorator Return Types**
Decorators can return modified property descriptors.

---

## **9. Example: Creating Autobind Decorator**

```ts
function Autobind(_: any, _2: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;
  return {
    configurable: true,
    enumerable: false,
    get() {
      return originalMethod.bind(this);
    },
  };
}
class Printer {
  message = "Hello!";
  @Autobind
  showMessage() {
    console.log(this.message);
  }
}
const p = new Printer();
document.querySelector("button")!.addEventListener("click", p.showMessage);
```

---

## **10. Validation with Decorators**
Decorators can be used for input validation.

```ts
function Required(target: any, propName: string) {
  console.log("Required decorator!", target, propName);
}
class Course {
  @Required
  title: string;
  constructor(title: string) {
    this.title = title;
  }
}
```

---

This covers the basics of TypeScript decorators! 🚀
