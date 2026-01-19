---

# ✅ Introduction to Utility Types

**Utility Types** are built-in TypeScript helpers that **transform existing types** instead of creating new ones from scratch.

They help reduce repetition and make code safer and cleaner.

---

# ✅ Commonly Used Utility Types

---

## 1️⃣ `Partial<T>`

**Definition:**
Makes **all properties optional**.

```ts
type User = {
  name: string
  age: number
}

type PartialUser = Partial<User>

const user: PartialUser = {
  name: "Alex"
}
```

---

## 2️⃣ `Required<T>`

**Definition:**
Makes **all properties required**.

```ts
type User = {
  name?: string
  age?: number
}

type RequiredUser = Required<User>

const user: RequiredUser = {
  name: "Alex",
  age: 25
}
```

---

## 3️⃣ `Readonly<T>`

**Definition:**
Prevents properties from being **modified**.

```ts
type User = {
  name: string
  age: number
}

const user: Readonly<User> = {
  name: "Alex",
  age: 25
}

// user.age = 30 ❌ Error
```

---

## 4️⃣ `Record<K, T>`

**Definition:**
Creates an object type with **fixed key type** and **value type**.

```ts
type Scores = Record<string, number>

const marks: Scores = {
  math: 90,
  english: 85
}
```

---

## 5️⃣ `Pick<T, K>`

**Definition:**
Selects **specific properties** from a type.

```ts
type User = {
  name: string
  age: number
  email: string
}

type UserPreview = Pick<User, "name" | "age">

const user: UserPreview = {
  name: "Alex",
  age: 25
}
```

---

## 6️⃣ `Omit<T, K>`

**Definition:**
Removes **specific properties** from a type.

```ts
type User = {
  name: string
  age: number
  password: string
}

type SafeUser = Omit<User, "password">
```

---

## 7️⃣ `Exclude<T, U>`

**Definition:**
Removes types from a **union**.

```ts
type Status = "success" | "error" | "loading"

type FinalStatus = Exclude<Status, "loading">
// "success" | "error"
```

---

## 8️⃣ `Extract<T, U>`

**Definition:**
Keeps only the **matching types** from a union.

```ts
type Status = "success" | "error" | "loading"

type OnlyError = Extract<Status, "error" | "warning">
// "error"
```

---

## 9️⃣ `NonNullable<T>`

**Definition:**
Removes `null` and `undefined` from a type.

```ts
type Value = string | null | undefined

type CleanValue = NonNullable<Value>
// string
```

---

# 🧠 Quick Summary Table

| Utility Type  | One-line Purpose              |
| ------------- | ----------------------------- |
| `Partial`     | Makes all fields optional     |
| `Required`    | Makes all fields required     |
| `Readonly`    | Prevents modification         |
| `Record`      | Creates key-value object type |
| `Pick`        | Selects properties            |
| `Omit`        | Removes properties            |
| `Exclude`     | Removes union members         |
| `Extract`     | Keeps matching union members  |
| `NonNullable` | Removes null & undefined      |

---

### ✅ One-line takeaway

> **Utility Types help you reuse and transform types safely without rewriting code.**

