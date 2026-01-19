---

# 🔷 Interface with Class in TypeScript

### 📌 One-line definition

> An **interface** defines a structure (what a class must have), and a **class implements that interface**.

---

## 🔹 Why use Interface with Class?

✔ Enforces a contract
✔ Ensures consistency
✔ Helps in large projects
✔ Improves readability

---

## 🔹 Basic Example

### Step 1: Define an Interface

```ts
interface Person {
  name: string;
  age: number;
  greet(): void;
}
```

---

### Step 2: Implement Interface in Class

```ts
class Student implements Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  greet(): void {
    console.log("Hello, my name is", this.name);
  }
}
```

---

### Step 3: Use the Class

```ts
const s1 = new Student("Alice", 20);
s1.greet();
```

---

## 🔹 What if class misses something? ❌

```ts
class Teacher implements Person {
  name: string;
  // age missing ❌

  greet() {
    console.log("Hi");
  }
}
```

👉 TypeScript error:
**Property 'age' is missing**

---

## 🔹 Real-World Example

### Payment System

```ts
interface Payment {
  pay(amount: number): void;
}

class CreditCardPayment implements Payment {
  pay(amount: number): void {
    console.log("Paid", amount, "using Credit Card");
  }
}

class UpiPayment implements Payment {
  pay(amount: number): void {
    console.log("Paid", amount, "using UPI");
  }
}
```

Usage:

```ts
const payment: Payment = new CreditCardPayment();
payment.pay(500);
```

---

## 🧠 Key Rules

✔ Class uses `implements` (not `extends`)
✔ Interface defines **what**, class defines **how**
✔ Class must implement **all** interface members

---

## 🆚 Interface vs Class (Quick)

| Interface      | Class           |
| -------------- | --------------- |
| Blueprint      | Implementation  |
| No logic       | Has logic       |
| No constructor | Has constructor |

---

### ⭐ One-line takeaway

> **Interfaces enforce structure; classes provide behavior.**

