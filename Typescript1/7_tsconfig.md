
---

# TypeScript Configuration File (`tsconfig.json`)

---

## 1. What is `tsconfig.json`?

**Definition:**
`tsconfig.json` is a configuration file that tells the **TypeScript compiler (`tsc`) how to compile your TypeScript code**.

In simple words:
➡ It controls **rules, behavior, and output** of TypeScript.

---

## 2. Why Do We Need `tsconfig.json`?

Without `tsconfig.json`:

* You must pass options manually every time
* No centralized control
* Hard to manage large projects

With `tsconfig.json`:

* One-time configuration
* Consistent compilation
* Better error checking
* Cleaner project structure

---

## 3. How to Generate `tsconfig.json`

Run this command in your project root:

```bash
tsc --init
```

✅ This creates a default `tsconfig.json` file with comments.

---

## 4. Basic Structure of `tsconfig.json`

```json
{
  "compilerOptions": {
    // compiler rules go here
  },
  "include": [],
  "exclude": []
}
```

---

## 5. Important & Useful Compiler Options

### 5.1 `target` – JavaScript Version

**Definition:**
Specifies which JavaScript version TypeScript should compile to.

```json
"target": "ES6"
```

**Common values:**

* `ES5` → Old browsers
* `ES6 / ES2015` → Modern browsers
* `ESNext` → Latest JS features

📌 **Real-world use:**
Use `ES5` for legacy support, `ES6+` for modern apps.

---

### 5.2 `outDir` – Output Directory

**Definition:**
Specifies where compiled JavaScript files will be stored.

```json
"outDir": "./dist"
```

📁 Example:

```
src/app.ts   → dist/app.js
```

➡ Keeps source and output files cleanly separated.

---

### 5.3 `rootDir` – Source Directory

**Definition:**
Specifies where TypeScript source files are located.

```json
"rootDir": "./src"
```

---

### 5.4 `strict` – Enable Strict Type Checking

**Definition:**
Enables all strict type-checking rules.

```json
"strict": true
```

Includes:

* `strictNullChecks`
* `noImplicitAny`
* `strictFunctionTypes`

📌 **Highly recommended** for production apps.

---

### 5.5 `strictNullChecks`

**Definition:**
Prevents assigning `null` or `undefined` to variables unless explicitly allowed.

```json
"strictNullChecks": true
```

---

### 5.6 `module` – Module System

**Definition:**
Specifies how modules are generated.

```json
"module": "commonjs"
```

Common values:

* `commonjs` → Node.js
* `esnext` → Modern JS frameworks

---

### 5.7 `sourceMap`

**Definition:**
Generates `.map` files for debugging TypeScript in browser.

```json
"sourceMap": true
```

📌 Useful for debugging.

---

### 5.8 `removeComments`

**Definition:**
Removes comments from compiled JavaScript.

```json
"removeComments": true
```

---

### 5.9 `noEmitOnError`

**Definition:**
Stops JavaScript generation if TypeScript errors exist.

```json
"noEmitOnError": true
```

---

### 5.10 `allowJs`

**Definition:**
Allows JavaScript files to be compiled with TypeScript.

```json
"allowJs": true
```

📌 Useful when migrating JS → TS.

---

## 6. Include and Exclude Files

### Include

```json
"include": ["src/**/*"]
```

➡ Compile only files inside `src`.

---

### Exclude

```json
"exclude": ["node_modules", "dist"]
```

➡ Prevents compiling unwanted files.

---

## 7. Example of a Practical `tsconfig.json`

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "rootDir": "./src",
    "outDir": "./dist",
    "strict": true,
    "sourceMap": true,
    "noEmitOnError": true
  },
  "include": ["src"],
  "exclude": ["node_modules"]
}
```

---

## 8. How TypeScript Uses `tsconfig.json`

Once created, just run:

```bash
tsc
```

➡ TypeScript automatically reads `tsconfig.json`
➡ Compiles all included files using the given rules

---

## 9. Common Mistakes & Pitfalls

❌ Forgetting `outDir` → messy project
❌ Not using `strict` → hidden bugs
❌ Wrong `target` → browser issues
❌ Compiling `node_modules` accidentally

---

## 10. Best Practices

✔ Always use `tsconfig.json`
✔ Enable `strict` mode
✔ Separate `src` and `dist`
✔ Use modern `target` when possible
✔ Enable `sourceMap` for debugging

---

## 🔑 One-Line Exam Summary

**`tsconfig.json` is the configuration file that controls how TypeScript compiles code, manages JavaScript version output, enforces type safety, and organizes project structure.**

---
