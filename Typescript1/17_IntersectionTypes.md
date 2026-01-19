

# 🔷 Intersection Types in TypeScript

### 📌 What are Intersection Types?

**Intersection Types** allow you to **combine multiple types into one**
👉 Think of them like the **AND (`&`) operator**

```ts
type A = { a: number };
type B = { b: string };

type C = A & B;
```

✔ `C` must contain **both** `a` **and** `b`

---

### 📌 What can be combined?

Intersection Types can combine:

* ✅ Two types
* ✅ Two interfaces
* ✅ Two classes
* ✅ Object shapes

---

## 🆚 Union vs Intersection (with code)

### 🔹 Union Type (`|`) → OR

> Value can be **either one**

```ts
type Admin = {
  permissions: string[];
};

type User = {
  name: string;
};

type Account = Admin | User;
```

✔ Valid:

```ts
const a: Account = { name: "John" };
const b: Account = { permissions: ["read"] };
```

❌ Not required to have both

---

### 🔹 Intersection Type (`&`) → AND

> Value must have **everything**

```ts
type Admin = {
  permissions: string[];
};

type User = {
  name: string;
};

type AdminUser = Admin & User;
```

✔ Must include **both properties**

```ts
const admin: AdminUser = {
  name: "John",
  permissions: ["read", "write"]
};
```

---

## 📦 Real-world Example (Object Combination)

### Without Intersection (bad practice)

```ts
function createUser(data: {
  id: number;
  name: string;
  email: string;
}) {}
```

### With Intersection (clean & reusable)

```ts
type HasId = {
  id: number;
};

type UserInfo = {
  name: string;
  email: string;
};

type User = HasId & UserInfo;
```

✔ Easy to maintain
✔ Reusable types

---

## 🧠 Quick Comparison Table

| Feature | Union (`|`) | Intersection (`&`) |
|------|------------|------------------|
| Meaning | OR | AND |
| Properties required | Any one | All |
| Common use | Conditional shapes | Combining features |
| Example | `A \| B` | `A & B` |

---

## ⭐ When to use Intersection Types

✔ Combining multiple object types
✔ Merging API response shapes
✔ Reusable function parameters
✔ React component props
✔ Feature-based design

---

### 🧠 One-line summary

> **Union → choose one**
> **Intersection → combine all**


### Summary

# Intersection Types

=> Intersection Types allow you to combine multiple types into one. (like AND operator )
=> It can combine two types , two interfaces and Two classes.
=> we use it suppose we have to combine two object so 1st we have to combine their types or interfaces.


## Union vs Interesction 

Union is like OR (we can choose any one)
Intersection is like AND (it combines both)



