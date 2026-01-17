
---

# 📌 Array Data Types in TypeScript

### 🔹 Definition (One line)

**An array is a collection of elements of the same data type stored in a single variable.**

### ✅ Examples

```ts
let numbers: number[] = [1, 2, 3];
let names: Array<string> = ["A", "B"];
```

---

## 🔒 Readonly Array

A **readonly array** prevents modification like `push`, `pop`, or reassignment of elements.

### ✅ Syntax

```ts
let names: ReadonlyArray<string> = ["A", "B"];
```

or (modern & recommended)

```ts
let names: readonly string[] = ["A", "B"];
```

### ❌ Not Allowed

```ts
names.push("C");   // ❌ Error
names[0] = "Z";    // ❌ Error
```

### ✅ Allowed

```ts
console.log(names[0]); // ✅ Read-only access
```

---

# 📌 Tuple Data Types in TypeScript

### 🔹 Definition (One line)

**A tuple is an ordered collection of fixed length where each element has a specific data type.**

---

## ✅ Tuple Example

```ts
let person: [string, number] = ["Alice", 25];
```

* Index `0` → string
* Index `1` → number
* Length is fixed

---

## ⚠️ Tuple Mutability Issue

Even though tuples are fixed-length, **TypeScript allows `push()`**, which is unsafe:

```ts
person.push(30); // ❌ Allowed by TS but breaks tuple concept
```

---

## 🔒 Readonly Tuple (Solution)

To fully protect a tuple, make it **readonly**.

### ✅ Syntax

```ts
let person: readonly [string, number] = ["Alice", 25];
```

### ❌ Not Allowed

```ts
person[0] = "Bob";  // ❌ Error
person.push(30);    // ❌ Error
```

### ✅ Allowed

```ts
console.log(person[1]); // ✅
```

---

# 📊 Array vs Tuple (Difference Table)

| Feature          | Array                 | Tuple                     |
| ---------------- | --------------------- | ------------------------- |
| Length           | Dynamic               | Fixed                     |
| Data Types       | Same type             | Different types allowed   |
| Order            | Ordered               | Ordered                   |
| Type Safety      | Less strict           | More strict               |
| Push/Pop         | Allowed               | Allowed (unless readonly) |
| Readonly Support | `ReadonlyArray<T>`    | `readonly [T1, T2]`       |
| Use Case         | List of similar items | Structured data           |

---

# 📊 Normal vs Readonly (Quick Comparison)

| Type           | Can Modify   | Can Push |
| -------------- | ------------ | -------- |
| Array          | ✅ Yes        | ✅ Yes    |
| Readonly Array | ❌ No         | ❌ No     |
| Tuple          | ⚠️ Partially | ⚠️ Yes   |
| Readonly Tuple | ❌ No         | ❌ No     |

---


