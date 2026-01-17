# Symbol DataType

This is the unique DataType that always generate a unique value.
Any two symbol can not be same.
Introduced in ES6.


---

# Symbol Data Type in TypeScript

---

## 1. What Is Symbol?

**Definition:**
`Symbol` is a **primitive data type** that always creates a **unique value**, even if two symbols have the same description.

✔ Introduced in **ES6 (ES2015)**
✔ Every symbol is **guaranteed to be unique**

---

## 2. Why Do We Need Symbol? (First-Principle Thinking)

### The Problem

In JavaScript/TypeScript, object property names are usually strings.

```ts
let user = {
  id: 1,
  id: 2 // ❌ overwritten
};
```

➡ Property name collision can happen.

### The Solution

**Symbol creates unique keys** that cannot clash with other properties.

---

## 3. Creating a Symbol

```ts
let id: symbol = Symbol("id");
```

➡ `"id"` is just a description, **not the value**.

---

## 4. Symbols Are Always Unique

```ts
let s1 = Symbol("key");
let s2 = Symbol("key");

console.log(s1 === s2); // false
```

✔ Even with the same description, symbols are different.

---

## 5. Using Symbol as Object Property (Main Use Case)

```ts
const userId = Symbol("userId");

let user = {
  name: "Alice",
  [userId]: 101
};

console.log(user[userId]); // 101
```

✔ The symbol property does not conflict with normal keys.

---

## 6. Symbol in TypeScript (Type Safety)

```ts
let token: symbol = Symbol("token");
```

⚠️ Cannot assign another symbol type:

```ts
let a: symbol = Symbol("a");
let b: symbol = Symbol("b");

a = b; // ❌ Error in strict mode
```

---

## 7. Global Symbols (`Symbol.for`)

**Definition:**
Creates or retrieves a shared symbol from a global registry.

```ts
let s1 = Symbol.for("appId");
let s2 = Symbol.for("appId");

console.log(s1 === s2); // true
```

✔ Useful when different files/modules need the same symbol.

---

## 8. Real-World Use Cases of Symbol

### 8.1 Unique Object IDs

```ts
const ID = Symbol("ID");
```

---

### 8.2 Avoiding Property Name Conflicts (Libraries / Frameworks)

```ts
const internal = Symbol("internal");
```

---

### 8.3 Private-Like Properties

```ts
const password = Symbol("password");

class User {
  [password]: string = "secret";
}
```

➡ Not accessible accidentally.

---

### 8.4 Custom Iterators

```ts
let numbers = {
  values: [1, 2, 3],
  [Symbol.iterator]() {
    return this.values[Symbol.iterator]();
  }
};
```

---

## 9. Limitations of Symbol

❌ Symbols cannot be converted to strings directly
❌ Not visible in `JSON.stringify()`
❌ Not enumerable in `for...in` loops

```ts
JSON.stringify({ [Symbol("x")]: 10 }); // {}
```

---

## 10. Symbol vs String Keys

| Feature            | Symbol        | String       |
| ------------------ | ------------- | ------------ |
| Uniqueness         | Always unique | Can conflict |
| Property collision | No            | Yes          |
| JSON support       | No            | Yes          |
| Visibility         | Hidden        | Visible      |

---

## 🔑 One-Line Exam Summary

**Symbol is a primitive data type introduced in ES6 that creates unique values, mainly used to avoid object property conflicts and to define hidden or internal properties in TypeScript applications.**

---

