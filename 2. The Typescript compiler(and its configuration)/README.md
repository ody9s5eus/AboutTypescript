# The Typescript compiler(and its configuration)

tags: #TypeScript #Compiler #Configuration  

---

## **1. Using Watch Mode**
TypeScript provides a `--watch` mode to automatically recompile files when changes are detected.

```sh
tsc --watch
```

This keeps TypeScript running in the background, re-compiling when files are modified.

---

## **2. Compiling Entry Project / Multiple Files**

### **📌 Compiling a Single File**
```sh
tsc index.ts
```

### **📌 Compiling Multiple Files**
```sh
tsc file1.ts file2.ts
```

### **📌 Compiling an Entire Project**
If you have a `tsconfig.json`, simply run:
```sh
tsc
```

---

## **3. Including & Excluding Files**
You can specify files to include or exclude in `tsconfig.json`:

```json
{
  "include": ["src/**/*"],
  "exclude": ["node_modules", "dist"]
}
```

---

## **4. Setting a Compilation Target**
Define the JavaScript version output:

```json
{
  "compilerOptions": {
    "target": "ES6"
  }
}
```

---

## **5. Understanding TypeScript Core Libs**
By default, TypeScript includes core JavaScript libraries like `ES5`, `ES6`, `DOM`, etc.
You can specify which libraries to use:

```json
{
  "compilerOptions": {
    "lib": ["ES6", "DOM"]
  }
}
```

---

## **6. More Configurations & Compilation Options**
TypeScript provides numerous compiler options to fine-tune your setup:

```json
{
  "compilerOptions": {
    "removeComments": true,
    "noImplicitAny": true
  }
}
```

---

## **7. Working with Source Maps**
To enable debugging, generate source maps:

```json
{
  "compilerOptions": {
    "sourceMap": true
  }
}
```

---

## **8. rootDir & outDir**
Organize compiled output using:

```json
{
  "compilerOptions": {
    "rootDir": "src",
    "outDir": "dist"
  }
}
```

---

## **9. Stop Emitting Files on Compilation Errors**
Prevent output files from being generated when there are errors:

```json
{
  "compilerOptions": {
    "noEmitOnError": true
  }
}
```

---

## **10. Strict Compilation**
Enable strict type-checking for better type safety:

```json
{
  "compilerOptions": {
    "strict": true
  }
}
```

---

## **11. Code Quality Options**
Improve code quality with these settings:

```json
{
  "compilerOptions": {
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true
  }
}
```

---

## **12. Debugging with VS Code**
VS Code supports TypeScript debugging using source maps.

1. Enable `sourceMap` in `tsconfig.json`.
2. Create a `.vscode/launch.json` file:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Debug TypeScript",
      "program": "${workspaceFolder}/src/index.ts",
      "outFiles": ["${workspaceFolder}/dist/**/*.js"]
    }
  ]
}
```
```

Now, press `F5` to start debugging!

---

These configurations help you optimize and customize your TypeScript compilation process. 🚀
