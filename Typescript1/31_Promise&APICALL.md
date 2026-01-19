

---

# 🔹 Promise in TypeScript

## What is a Promise? (Easy language)

> A **Promise** represents a value that will be available **in the future**
> (success or failure).

It has **3 states**:

* ⏳ Pending
* ✅ Fulfilled
* ❌ Rejected

---

## Basic Promise Example

```ts
const myPromise: Promise<string> = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Hello TypeScript")
  }, 1000)
})
```

Using the promise:

```ts
myPromise.then(result => {
  console.log(result)
})
```

---

## Promise with Error

```ts
const promiseWithError: Promise<number> = new Promise((_, reject) => {
  reject("Something went wrong")
})

promiseWithError.catch(error => {
  console.error(error)
})
```

---

## 🔹 Async / Await (Recommended)

```ts
async function getMessage(): Promise<string> {
  return "Hello"
}
```

Usage:

```ts
const msg = await getMessage()
console.log(msg)
```

---

# 🌐 API Call in TypeScript

TypeScript uses the **same APIs as JavaScript**, but with **types**.

Most common ways:

* `fetch` (browser / Node 18+)
* `axios` (library)

---

## 1️⃣ API Call using `fetch`

### Example: GET request

```ts
type User = {
  id: number
  name: string
  email: string
}

async function fetchUsers(): Promise<User[]> {
  const response = await fetch("https://jsonplaceholder.typicode.com/users")

  if (!response.ok) {
    throw new Error("Failed to fetch users")
  }

  const data: User[] = await response.json()
  return data
}
```

Usage:

```ts
fetchUsers()
  .then(users => console.log(users))
  .catch(err => console.error(err))
```

---

## 2️⃣ API Call using `axios` (popular)

Install:

```bash
npm install axios
```

Example:

```ts
import axios from "axios"

type Post = {
  id: number
  title: string
}

async function fetchPosts(): Promise<Post[]> {
  const response = await axios.get<Post[]>(
    "https://jsonplaceholder.typicode.com/posts"
  )

  return response.data
}
```

---

## 3️⃣ POST API Call Example

```ts
type NewUser = {
  name: string
  email: string
}

async function createUser(user: NewUser): Promise<void> {
  await fetch("https://api.example.com/users", {
    method: "POST",
    headers: {
      "Content-Type": "application/json"
    },
    body: JSON.stringify(user)
  })
}
```

---

# 🏢 Real-World Example (API + Promise)

```ts
async function login(username: string, password: string): Promise<boolean> {
  const response = await fetch("/api/login")
  const result: { success: boolean } = await response.json()

  return result.success
}
```

---

# ⚠️ Common Mistakes

❌ Forgetting `await`
❌ Not typing API response
❌ Not handling errors

---

# 🧠 One-line summary

* **Promise** → handles async results (future values)
* **async/await** → clean way to use promises
* **API calls in TS** → same as JS but with **type safety**

---

