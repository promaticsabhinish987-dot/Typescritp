
---

# 🔍 Type Guard in TypeScript

### 📌 One-line definition

> A **Type Guard** is a way to **narrow down a variable’s type at runtime** so TypeScript knows exactly what type it is.

---

## ❌ The Problem (Without Type Guards)

```ts
function printId(id: string | number) {
  console.log(id.toUpperCase()); // ❌ Error
}
```

👉 TypeScript doesn’t know if `id` is a `string` or a `number`.

---

## ✅ The Solution (Type Guard)

```ts
function printId(id: string | number) {
  if (typeof id === "string") {
    console.log(id.toUpperCase()); // ✅
  } else {
    console.log(id.toFixed(2)); // ✅
  }
}
```

---

# 🧠 Types of Type Guards

---

## 1️⃣ `typeof` Type Guard (Primitives)

### Used for:

`string`, `number`, `boolean`, `symbol`, `undefined`

```ts
function formatValue(value: string | number) {
  if (typeof value === "number") {
    return value.toFixed(2);
  }
  return value.toUpperCase();
}
```

### ✅ Real-world use

Handling form input values or API responses

---

## 2️⃣ `instanceof` Type Guard (Classes)

### Used for:

Class-based objects

```ts
class Dog {
  bark() {}
}

class Cat {
  meow() {}
}

function makeSound(animal: Dog | Cat) {
  if (animal instanceof Dog) {
    animal.bark();
  } else {
    animal.meow();
  }
}
```

### ✅ Real-world use

OOP-based systems (Payments, Notifications)

---

## 3️⃣ `in` Operator Type Guard (Objects)

### Used for:

Checking property existence

```ts
type Admin = { role: "admin"; permissions: string[] };
type User = { role: "user"; name: string };

function handleUser(person: Admin | User) {
  if ("permissions" in person) {
    console.log(person.permissions);
  } else {
    console.log(person.name);
  }
}
```

### ✅ Real-world use

Authorization & role-based access

---

## 4️⃣ Custom Type Guard (User-Defined)

### Syntax

```ts
function isAdmin(user: any): user is Admin {
  return user.role === "admin";
}
```

### Usage

```ts
function processUser(user: Admin | User) {
  if (isAdmin(user)) {
    console.log(user.permissions);
  } else {
    console.log(user.name);
  }
}
```

### ✅ Real-world use

API response validation

---

## 5️⃣ Discriminated Union (Best Practice)

### Example

```ts
type Success = { status: "success"; data: string };
type ErrorRes = { status: "error"; message: string };

function handleResponse(res: Success | ErrorRes) {
  if (res.status === "success") {
    console.log(res.data);
  } else {
    console.log(res.message);
  }
}
```

### ✅ Real-world use

API responses, Redux state

---

# 🧠 Summary Table

| Type Guard    | Used For      | Example                 |
| ------------- | ------------- | ----------------------- |
| `typeof`      | Primitives    | `typeof x === "string"` |
| `instanceof`  | Classes       | `obj instanceof Class`  |
| `in`          | Object props  | `"key" in obj`          |
| Custom        | Complex logic | `user is Admin`         |
| Discriminated | Clean unions  | `status: "success"`     |

---

### ⭐ One-line takeaway

> **Type Guards help TypeScript understand what type you’re working with at runtime.**

---
