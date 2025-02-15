# Getting Started with TypeScript

tags: #TypeScript #GettingStarted  

---

## **1. What is TypeScript & Why Should We Use It?**

TypeScript is a **strongly typed** superset of JavaScript that compiles to plain JavaScript. It enhances JavaScript by adding **static types**, making the code more maintainable and scalable.

### **📌 Why Use TypeScript?**
- **Static Typing**: Helps catch errors at compile time.
- **Better Code Completion**: IDEs provide enhanced autocompletion and suggestions.
- **Improved Maintainability**: Easier to refactor and understand large codebases.
- **Modern JavaScript Features**: Supports ES6+ syntax and compiles down to compatible JavaScript.

```ts
// TypeScript example
let message: string = "Hello, TypeScript!";
console.log(message);
```

---

## **2. Installing & Using TypeScript**

To install TypeScript globally, use npm:

```sh
npm install -g typescript
```

Verify the installation:

```sh
tsc --version
```

You can also install TypeScript locally within a project:

```sh
npm install --save-dev typescript
```

To compile a TypeScript file (`app.ts`) into JavaScript:

```sh
tsc app.ts
```

This generates `app.js`, which can be executed with Node.js:

```sh
node app.js
```

---

## **3. Setting Up the Editor**

### **📌 Using VS Code**
VS Code is one of the best editors for TypeScript.

1. Download & install [VS Code](https://code.visualstudio.com/).
2. Install the **TypeScript Language Support** extension (optional).
3. Open your project folder and create a TypeScript file (`index.ts`).
4. Compile and run the file using `tsc`.

### **📌 Configuring TypeScript Project**
To configure TypeScript settings, create a `tsconfig.json` file:

```sh
tsc --init
```

This generates a default `tsconfig.json`, where you can specify compiler options:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "CommonJS",
    "strict": true,
    "outDir": "./dist"
  }
}
```

Now, compile the entire project:

```sh
tsc
```

---

With these steps, you’re ready to start coding in TypeScript! 🚀
