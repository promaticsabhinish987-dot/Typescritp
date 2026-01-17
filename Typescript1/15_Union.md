
---

# 📌 Union Types in TypeScript

### 🔹 Definition (One line)

**A union type allows a variable, parameter, or return value to hold one of multiple specified data types.**

---

## ✨ Why Union Types Are Unique

> **Union types provide flexibility while maintaining type safety.**

**Uniqueness:**

* Accepts **multiple types**
* Prevents invalid values
* Forces **type narrowing** before using specific properties
* Safer alternative to `any`

---

## 📍 Different Uses of Union Types

---

## 1️⃣ Union with Variables

```ts
let id: number | string;

id = 101;      // ✅
id = "A102";   // ✅
id = true;     // ❌ Error
```

---

## 2️⃣ Union with Function Parameters

```ts
function printId(id: number | string): void {
  console.log(id);
}
```

---

## 3️⃣ Union with Function Return Type

```ts
function getValue(value: number): number | string {
  return value > 0 ? value : "Invalid number";
}
```

---

## 4️⃣ Union with Arrays

Array elements can be of multiple types.

```ts
let data: (number | string)[] = [1, "A", 2, "B"];
```

---

## 5️⃣ Union with Objects

```ts
let user: { name: string } | { id: number };

user = { name: "Alice" }; // ✅
user = { id: 101 };       // ✅
```

---

## 6️⃣ Union with Optional Values

```ts
function showMessage(msg: string | null): void {
  if (msg !== null) {
    console.log(msg.toUpperCase());
  }
}
```

---

## 7️⃣ Union with Literal Types

Restricts values to specific options.

```ts
let status: "success" | "error" | "loading";

status = "success"; // ✅
status = "done";    // ❌
```

---

## 8️⃣ Union with Tuples

```ts
let response: [number, string] | [string, string];

response = [200, "OK"];
response = ["Error", "Failed"];
```

---

## 9️⃣ Union with Type Narrowing (Important)

TypeScript requires **checks** before using specific methods.

```ts
function process(value: string | number): void {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}
```

---

## 1️⃣0️⃣ Union vs Any (Key Difference)

```ts
let value: any = "Hello";
value.toUpperCase(); // ✅ allowed

let data: string | number = "Hello";
// data.toUpperCase(); // ❌ Error (needs type check)
```

---

## 🆚 Union vs Intersection

| Feature | Union (`|`) | Intersection (`&`) |
|----|----|----|
Meaning | One of many types | Combination of all types |
Flexibility | High | Strict |
Use Case | Variable data | Merging objects |

---

## 📌 Best Practices

* Use unions instead of `any`
* Always perform **type narrowing**
* Combine with literal types for better control
* Keep unions simple and readable

---

## 📌 Summary

* Union uses `|`
* Allows multiple types safely
* Forces validation before usage
* Improves code flexibility
* Prevents runtime errors

---

## 🏆 Final Takeaway

> **Union types are unique because they balance flexibility and safety, making TypeScript both powerful and reliable.**

---
