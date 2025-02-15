# Generics

tags: #TypeScript #Generics  

---

## **1. Built-in Generics & What are Generics?**
Generics provide a way to create reusable components.

```ts
function identity<T>(arg: T): T {
  return arg;
}
console.log(identity<number>(5));
console.log(identity<string>("Hello"));
```

---

## **2. Creating a Generic Function**

```ts
function wrapInArray<T>(value: T): T[] {
  return [value];
}
console.log(wrapInArray("hello"));
```

---

## **3. Working with Constraints**

```ts
function logLength<T extends { length: number }>(item: T): void {
  console.log(item.length);
}
logLength("Hello");
```

---

## **4. Another Generic Function**

```ts
function merge<T, U>(obj1: T, obj2: U): T & U {
  return { ...obj1, ...obj2 };
}
console.log(merge({ name: "Alice" }, { age: 25 }));
```

---

## **5. The 'keyof' Constraint**

```ts
function getProperty<T, K extends keyof T>(obj: T, key: K) {
  return obj[key];
}
const user = { name: "Alice", age: 25 };
console.log(getProperty(user, "name"));
```

---

## **6. Generic Classes**

```ts
class DataStore<T> {
  private data: T[] = [];
  add(item: T) {
    this.data.push(item);
  }
  getItems() {
    return this.data;
  }
}
const store = new DataStore<number>();
store.add(10);
console.log(store.getItems());
```

---

## **7. Generic Utility Types**

```ts
type PartialUser = Partial<{ name: string; age: number }>;
```

---

## **8. Generic Types & Union Types**

```ts
type ApiResponse<T> = T | { error: string };
const success: ApiResponse<string> = "Data loaded successfully";
const failure: ApiResponse<string> = { error: "Failed to load data" };
```

---

These generic features enhance TypeScript's flexibility! 🚀