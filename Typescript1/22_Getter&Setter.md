
---

# 🔒 Getter and Setter in TypeScript

## ❌ The Problem (Without Getter & Setter)

### What goes wrong?

* Class properties are **directly accessible**
* Anyone can assign **invalid values**
* No control over **how data is read or updated**

### Example (Problem)

```ts
class BankAccount {
  public balance: number = 0;
}

const account = new BankAccount();
account.balance = -1000; // ❌ invalid but allowed
```

👉 This breaks business rules (balance should not be negative)

---

## ✅ The Solution (Getter & Setter)

### What do getters & setters do?

> **Getters and setters control access to class properties**
> They allow **validation, formatting, and protection**.

---

## 🔹 Using Getter & Setter

```ts
class BankAccount {
  private _balance: number = 0;

  // Getter (read value)
  get balance(): number {
    return this._balance;
  }

  // Setter (update value)
  set balance(amount: number) {
    if (amount < 0) {
      throw new Error("Balance cannot be negative");
    }
    this._balance = amount;
  }
}
```

### Usage

```ts
const account = new BankAccount();

account.balance = 500;   // calls setter ✅
console.log(account.balance); // calls getter ✅

// account.balance = -100; ❌ Error
```

---

## 🧠 What Just Happened?

* `balance = 500` → calls **setter**
* `balance` → calls **getter**
* Internal data (`_balance`) is **protected**
* Invalid updates are **blocked**

---

## 🌍 Real-World Example

### User Age Validation

```ts
class User {
  private _age: number = 0;

  get age(): number {
    return this._age;
  }

  set age(value: number) {
    if (value < 18) {
      throw new Error("User must be 18+");
    }
    this._age = value;
  }
}
```

---

## 🆚 Without vs With Getter/Setter

| Without          | With                |
| ---------------- | ------------------- |
| No validation    | Validation possible |
| Direct access    | Controlled access   |
| Unsafe data      | Safe data           |
| Hard to maintain | Easy to maintain    |

---

## ⭐ When to use Getter & Setter

✔ When validation is needed
✔ When business rules apply
✔ When properties should be protected
✔ When internal logic may change later

---

### 🧠 One-line takeaway

> **Getters and setters protect class data while keeping access simple.**

