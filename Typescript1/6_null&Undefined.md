
---

# `null` and `undefined` in TypeScript

---

## 1. What is `undefined`?

**Definition:**
`undefined` means a variable has been **declared but not assigned any value**.

```ts
let x: number;
console.log(x); // undefined
```

### When does `undefined` appear?

* Variable is declared but not initialized
* Function does not return a value
* Missing function parameter
* Object property does not exist

```ts
function demo() {}
console.log(demo()); // undefined
```

---

## 2. What is `null`?

**Definition:**
`null` represents an **intentional empty or missing value** assigned by the programmer.

```ts
let y: null = null;
```

### When is `null` used?

* To explicitly say “no value”
* To reset or clear a variable
* To represent empty data from database/API

---

## 3. Data Type of `null` and `undefined`

```ts
typeof undefined; // "undefined"
typeof null;      // "object"  ❗ (JavaScript bug)
```

➡ `typeof null === "object"` is a **known JavaScript design mistake**, but it still exists for backward compatibility.

---

## 4. Differences Between `null` and `undefined`

| Feature                 | undefined     | null                |
| ----------------------- | ------------- | ------------------- |
| Meaning                 | Not assigned  | Intentionally empty |
| Assigned by             | JavaScript    | Developer           |
| Type                    | undefined     | object (JS bug)     |
| Use case                | Missing value | Known empty value   |
| Equality (`==`)         | Equal to null | Equal to undefined  |
| Strict equality (`===`) | Not equal     | Not equal           |

```ts
null == undefined;  // true
null === undefined; // false
```

---

## 5. Why Do We Have Both?

From first principles:

* **`undefined`** → system-level absence (default, accidental, missing)
* **`null`** → business-level absence (intentional, meaningful)

This separation allows:

* Clear intent in code
* Better error handling
* More accurate modeling of real-world data

---

## 6. Real-World Usage Examples

### Example 1: User data from API

```ts
type User = {
  name: string;
  email: string | null;
};
```

➡ Email may exist or may be intentionally empty.

---

### Example 2: Optional function parameter

```ts
function greet(name?: string) {
  console.log(name);
}
```

➡ Missing parameter → `undefined`

---

### Example 3: Resetting a value

```ts
let selectedUser: number | null = null;
selectedUser = 10;
selectedUser = null; // reset
```

---

## 7. Using `null` and `undefined` with Union Types

```ts
let age: number | null;
let score: number | undefined;
```

### Both allowed:

```ts
let data: number | null | undefined;
```

➡ Useful when:

* Value may be missing (`undefined`)
* Value may be intentionally empty (`null`)

---

## 8. How to Handle `null` and `undefined` Safely

### 8.1 Null Checks

```ts
if (value !== null) {
  console.log(value);
}
```

---

### 8.2 Undefined Checks

```ts
if (value !== undefined) {
  console.log(value);
}
```

---

### 8.3 Optional Chaining (`?.`)

```ts
user?.address?.city;
```

---

### 8.4 Nullish Coalescing (`??`)

```ts
let username = input ?? "Guest";
```

➡ Uses default only if value is `null` or `undefined`.

---

## 9. Strict Null Checks (Very Important)

```json
// tsconfig.json
{
  "strictNullChecks": true
}
```

➡ Prevents accidental use of `null` and `undefined`.

```ts
let n: number = null; // ❌ Error
```

---

## 10. Common Pitfalls and Mistakes

### Pitfall 1: Assuming value exists

```ts
let value: string | null;
console.log(value.length); // ❌ Error
```

✔ Fix:

```ts
if (value) console.log(value.length);
```

---

### Pitfall 2: Confusing null and undefined

```ts
Boolean("false"); // true
```

➡ Empty string ≠ null ≠ undefined

---

### Pitfall 3: Using `==` instead of `===`

```ts
null == undefined;  // true (confusing)
```

✔ Always use `===`.

---

## 11. Best Practices

✔ Use `undefined` for **optional or missing values**
✔ Use `null` for **intentional empty values**
✔ Enable `strictNullChecks`
✔ Use union types (`number | null`)
✔ Use `??` instead of `||` for defaults
✔ Avoid accessing properties without checks

---

## 🔑 One-Line Exam Summary

**`undefined` represents an uninitialized value, while `null` represents an intentional absence of value; TypeScript supports both to accurately model real-world data and improve code safety.**

---

