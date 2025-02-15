# Advanced Types

tags: #TypeScript #AdvancedTypes  

---

## **1. Intersection Types**
Intersection types allow combining multiple types into one.

```ts
interface User {
  name: string;
}
interface Admin {
  permissions: string[];
}
type AdminUser = User & Admin;
const admin: AdminUser = { name: "John", permissions: ["read", "write"] };
```

---

## **2. More on Type Guards**
Type guards allow narrowing down types at runtime.

```ts
function isString(value: unknown): value is string {
  return typeof value === "string";
}
function printLength(value: unknown) {
  if (isString(value)) {
    console.log(value.length);
  }
}
```

---

## **3. Discriminated Unions**
Using a common property to distinguish between different object types.

```ts
interface Circle {
  kind: "circle";
  radius: number;
}
interface Square {
  kind: "square";
  side: number;
}
type Shape = Circle | Square;
function getArea(shape: Shape) {
  if (shape.kind === "circle") return Math.PI * shape.radius ** 2;
  return shape.side ** 2;
}
```

---

## **4. Type Casting**
Forcing a variable into a specific type.

```ts
const input = document.getElementById("user-input") as HTMLInputElement;
input.value = "Hello";
```

---

## **5. Index Properties**
Allow defining flexible property keys.

```ts
interface ErrorContainer {
  [key: string]: string;
}
const errorBag: ErrorContainer = {
  email: "Invalid email format",
  username: "Username must be longer",
};
```

---

## **6. Function Overloads**
Allow defining multiple function signatures.

```ts
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: any, b: any) {
  return a + b;
}
console.log(add(1, 2));
console.log(add("Hello", " World"));
```

---

## **7. Optional Chaining**
Avoids errors when accessing deeply nested properties.

```ts
const user = { profile: { details: { age: 30 } } };
console.log(user?.profile?.details?.age);
```

---

## **8. Nullish Coalescing**
Provides a fallback only if a value is `null` or `undefined`.

```ts
const value = null ?? "Default Value";
console.log(value); // "Default Value"
```

---

These advanced TypeScript features help enhance type safety and code flexibility! 🚀
