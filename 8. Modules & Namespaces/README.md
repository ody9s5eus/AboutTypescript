# Modules & Namespaces

tags: #TypeScript #Modules #Namespaces  

---

## **1. Modules Introduction**
Modules in TypeScript help in organizing and reusing code by splitting it into separate files.

```ts
export function greet(name: string) {
  return `Hello, ${name}!`;
}
```

```ts
import { greet } from "./greet";
console.log(greet("Alice"));
```

---

## **2. Writing Module Code**
Modules can define reusable functionalities and export/import elements.

```ts
export class Person {
  constructor(public name: string) {}
}

export const age = 30;
```

```ts
import { Person, age } from "./person";
const p = new Person("Alice");
console.log(p.name, age);
```

---

## **3. Working with Namespaces**
Namespaces provide an internal module-like structure for grouping related functionalities.

```ts
namespace Utilities {
  export function log(message: string) {
    console.log("Log: ", message);
  }
}

Utilities.log("Hello");
```

---

## **4. Organizing Files and Folders**
A well-structured project organizes modules logically within folders:

```
project/
├── src/
│   ├── modules/
│   │   ├── math.ts
│   │   ├── string.ts
│   ├── app.ts
├── tsconfig.json
```

---

## **5. A Problem with Namespace Imports**
Namespaces are less commonly used due to dependency management complexities and global scope issues.

```ts
namespace App {
  export class User {
    constructor(public name: string) {}
  }
}
const user = new App.User("Alice");
```

---

## **6. Using ES Modules**
ES Modules are the recommended way to handle modular code in TypeScript.

```ts
import { add } from "./math.js";
console.log(add(2, 3));
```

---

## **7. Understanding Various Import/Export Syntaxes**
Different ways to import and export modules:

```ts
// Named exports
export function add(a: number, b: number) {
  return a + b;
}

// Default export
export default class Calculator {}
```

```ts
import { add } from "./math";
import Calculator from "./Calculator";
```

---

## **8. How Does Code in a Module Execute?**
Each module runs in its own scope and only exposes what it explicitly exports.

```ts
console.log("This executes when the module is imported");
```

---

Modules and namespaces help in structuring TypeScript projects efficiently! 🚀
