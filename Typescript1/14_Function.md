
---

# 📌 Functions in TypeScript

### 🔹 Definition (One line)

**A function in TypeScript is a reusable block of code with typed parameters and a typed return value.**

---

## 📍 Function Return Types

### 1️⃣ Function Returning a Value

If a function returns a value, we must specify its **data type**.

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

---

### 2️⃣ Function Not Returning a Value → `void`

If a function does **not return anything** and execution reaches the end.

```ts
function logMessage(msg: string): void {
  console.log(msg);
}
```

---

### 3️⃣ Function That Never Reaches the End → `never`

If a function **never completes execution**, use `never`.

Common cases:

* Throws an error
* Infinite loop

```ts
function throwError(message: string): never {
  throw new Error(message);
}
```

```ts
function infiniteLoop(): never {
  while (true) {}
}
```

---

## 📍 Function Parameter Types

### 1️⃣ Simple Parameters

```ts
function greet(name: string): string {
  return `Hello ${name}`;
}
```

---

### 2️⃣ Optional Parameters (`?`)

Optional parameters may or may not be passed.

```ts
function greetUser(name: string, age?: number): string {
  return age
    ? `Hello ${name}, Age: ${age}`
    : `Hello ${name}`;
}
```

📌 Optional parameters must come **after required ones**.

---

### 3️⃣ Default Parameters

```ts
function multiply(a: number, b: number = 1): number {
  return a * b;
}
```

---

### 4️⃣ Parameters with `any`

Allows passing any type (not recommended).

```ts
function printValue(value: any): void {
  console.log(value);
}
```

⚠️ **Disables type checking**

---

### 5️⃣ Parameters with `unknown` (Safer Alternative)

```ts
function processInput(input: unknown): void {
  if (typeof input === "string") {
    console.log(input.toUpperCase());
  }
}
```

---

## 📍 Function Type Expression

Define function structure separately.

```ts
let sum: (a: number, b: number) => number;

sum = (x, y) => x + y;
```

---

## 📍 Arrow Functions in TypeScript

```ts
const subtract = (a: number, b: number): number => {
  return a - b;
};
```

---

## 📍 Rest Parameters

Used to accept multiple arguments.

```ts
function total(...numbers: number[]): number {
  return numbers.reduce((a, b) => a + b, 0);
}
```

---

## 🆚 `void` vs `never`

| Feature       | `void`              | `never`                |
| ------------- | ------------------- | ---------------------- |
| Returns value | ❌                   | ❌                      |
| Reaches end   | ✅                   | ❌                      |
| Use case      | Logging, UI actions | Errors, infinite loops |

---

## 📌 Best Practices

* Always define **return types**
* Avoid `any`
* Prefer `unknown` for flexibility
* Use optional parameters carefully
* Use `never` only when function never ends

---

## 📌 Summary

* Use `number`, `string`, etc. for return types
* Use `void` if nothing is returned
* Use `never` if function never completes
* Use `?` for optional parameters
* Use `any` only when unavoidable

---

