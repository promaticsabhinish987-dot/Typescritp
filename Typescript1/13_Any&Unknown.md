---

# 📌 Any & Unknown in TypeScript

---

## 🔹 `any`

### ✅ Definition (One line)

**`any` allows a variable to hold any type of value and disables TypeScript type checking.**

### 📍 When to Use `any`

1. Migrating **JavaScript code to TypeScript**
2. Handling **API response data** with unknown structure
3. Working with **third-party libraries** without type definitions

### ⚠️ Important Note

> **`any` disables type safety**, so TypeScript will not report errors even if the code is wrong.

---

### 🧪 Example (`any`)

```ts
let value: any;

value = "Hello";
value = 10;
value = true;

console.log(value.toUpperCase()); // ✅ No error (but may crash at runtime)
```

❌ No compile-time error
❌ Unsafe

---

## 🔹 `unknown`

### ✅ Definition (One line)

**`unknown` is similar to `any`, but it enforces type checking before performing operations.**

### 🔐 Why `unknown` is Safer

* You **must check the type first**
* Prevents runtime errors
* Encourages safe coding practices

---

### 🧪 Example (`unknown`)

```ts
let name: unknown;

name = "TypeScript";

// ❌ Error
// name.toUpperCase();

if (typeof name === "string") {
  console.log(name.toUpperCase()); // ✅ Allowed after type check
}
```

✅ Compile-time safety
✅ Controlled usage

---

## 🆚 Any vs Unknown (Difference Table)

| Feature            | `any`                  | `unknown`                |
| ------------------ | ---------------------- | ------------------------ |
| Type Checking      | ❌ Disabled             | ✅ Required               |
| Safety             | ❌ Unsafe               | ✅ Safe                   |
| Operations Allowed | Without checks         | Only after checks        |
| Recommended        | ❌ Avoid if possible    | ✅ Preferred              |
| Use Case           | Quick fixes, migration | API data, safer handling |

---

## 📌 Key Takeaway

* Use **`any` only when necessary**
* Prefer **`unknown` for better type safety**
* `unknown` forces you to **validate before use**
* Helps avoid runtime errors

---

### ✅ Best Practice

> **Use `unknown` instead of `any` whenever possible.**

---


