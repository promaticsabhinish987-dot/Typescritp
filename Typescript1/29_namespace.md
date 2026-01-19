
---

# 📦 What is a Namespace in TypeScript?

**In simple words:**

> A **namespace** is a way to **group related code together** so names don’t clash.

Think of it like a **folder for code**.

---

## ❓ Why do we need namespaces?

Imagine this problem 👇

```ts
function log(message: string) {
  console.log(message)
}

function log(error: number) {
  console.log(error)
}
```

❌ Error: Same function name used twice.

---

## ✅ Solution: Namespace

```ts
namespace Logger {
  export function log(message: string) {
    console.log(message)
  }
}

namespace ErrorLogger {
  export function log(error: number) {
    console.log(error)
  }
}
```

Now you can use both safely:

```ts
Logger.log("App started")
ErrorLogger.log(404)
```

---

## 🔑 Key points about namespaces

* `namespace` groups related code
* `export` is required to access things outside
* Prevents **name conflicts**
* Mostly used in **large or legacy codebases**

---

## 🧩 Basic Namespace Example

```ts
namespace MathUtils {
  export function add(a: number, b: number): number {
    return a + b
  }

  export function multiply(a: number, b: number): number {
    return a * b
  }
}
```

Usage:

```ts
MathUtils.add(2, 3)
MathUtils.multiply(4, 5)
```

---

## 🏢 Real-World Use Case #1: Utility Library

```ts
namespace Auth {
  export function login(username: string, password: string) {
    return username === "admin"
  }

  export function logout() {
    console.log("Logged out")
  }
}
```

Usage:

```ts
Auth.login("admin", "1234")
Auth.logout()
```

---

## 🏢 Real-World Use Case #2: Models + Helpers

```ts
namespace UserModule {
  export interface User {
    id: number
    name: string
  }

  export function printUser(user: User) {
    console.log(user.name)
  }
}
```

Usage:

```ts
const user: UserModule.User = {
  id: 1,
  name: "Alex"
}

UserModule.printUser(user)
```

---

## 🔒 Without `export` (important!)

```ts
namespace Test {
  function secret() {
    console.log("hidden")
  }
}

Test.secret() // ❌ Error
```

Only exported members are accessible.

---

## ⚠️ Namespace vs ES Modules (Important)

| Namespace           | ES Module                |
| ------------------- | ------------------------ |
| Old / legacy        | Modern & recommended     |
| Uses `namespace`    | Uses `import` / `export` |
| Global scope        | File-based               |
| No bundler required | Works with bundlers      |

👉 **Modern TypeScript prefers ES Modules**, not namespaces.

---

## ❌ When NOT to use namespaces

* New projects
* React / Angular / Node apps
* When using `import/export`

---

## ✅ When to use namespaces

* Legacy JavaScript projects
* Code without modules
* Global utility libraries

---

## 🧠 One-line summary

> **Namespace = a container that groups related code and avoids name collisions.**

