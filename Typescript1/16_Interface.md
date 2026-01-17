
---

# 📌 Problem with Object Structure in TypeScript

### 🔹 What was the problem?

When we define object types **inline**, the structure:

* Is **not reusable**
* Becomes **hard to maintain**
* Causes **duplication**
* Is **difficult to extend**

---

## ❌ Object Structure Problem Example

```ts
let user1: {
  name: string;
  age: number;
} = {
  name: "Alice",
  age: 25
};

let user2: {
  name: string;
  age: number;
} = {
  name: "Bob",
  age: 30
};
```

### 🚫 Problems

* Structure is repeated
* If we add a new property, we must update everywhere
* Code is not scalable

---

# ✅ Solution: Interface

### 🔹 Definition (One line)

**An interface defines the structure of an object and makes it reusable, extendable, and maintainable.**

---

## ✅ Reusable Structure Using Interface

```ts
interface User {
  name: string;
  age: number;
}

let user1: User = {
  name: "Alice",
  age: 25
};

let user2: User = {
  name: "Bob",
  age: 30
};
```

✔ Reusable
✔ Clean
✔ Maintainable

---

# 🔁 How Interface Is Extendable

### 🔹 Extending an Interface

```ts
interface User {
  name: string;
  age: number;
}

interface Employee extends User {
  employeeId: number;
}

let emp: Employee = {
  name: "John",
  age: 28,
  employeeId: 101
};
```

### ✅ Benefits

* Avoids duplication
* Supports inheritance
* Follows DRY principle

---

# 📌 Other Uses of Interface

---

## 1️⃣ Interface with Optional Properties

```ts
interface User {
  name: string;
  age?: number;
}
```

---

## 2️⃣ Interface with Readonly Properties

```ts
interface User {
  readonly id: number;
  name: string;
}
```

---

## 3️⃣ Interface for Function Types

```ts
interface Add {
  (a: number, b: number): number;
}

const addNumbers: Add = (x, y) => x + y;
```

---

## 4️⃣ Interface for Arrays

```ts
interface StringArray {
  [index: number]: string;
}

let names: StringArray = ["A", "B"];
```

---

## 5️⃣ Interface with Nested Objects

```ts
interface Address {
  city: string;
  pincode: number;
}

interface User {
  name: string;
  address: Address;
}
```

---

## 6️⃣ Interface with Class (Implements)

```ts
interface Animal {
  sound(): void;
}

class Dog implements Animal {
  sound(): void {
    console.log("Bark");
  }
}
```

---

## 🆚 Object Type vs Interface

| Feature       | Object Type | Interface |
| ------------- | ----------- | --------- |
| Reusability   | ❌ No        | ✅ Yes     |
| Extending     | ❌ Hard      | ✅ Easy    |
| Readability   | ❌ Less      | ✅ Better  |
| Maintenance   | ❌ Difficult | ✅ Easy    |
| Class Support | ❌ No        | ✅ Yes     |

---

# 📌 Why Interface Is Powerful (Uniqueness)

* Enforces structure
* Supports extension
* Prevents duplication
* Improves scalability
* Used in large applications

---

## 📌 Summary

* Object structure was **not reusable**
* Interface solves duplication issues
* Interfaces are **extendable**
* Interfaces work with **objects, functions, arrays, and classes**
* Essential for **large-scale TypeScript applications**

---

### 🏆 Final Line

> **Interfaces make TypeScript code reusable, scalable, and maintainable by defining a clear contract.**

---
