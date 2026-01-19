
---

# 🔷 Enum in TypeScript

## 📌 What is an Enum?

An **Enum** is a data type that lets you define a **fixed set of named values**.

👉 Think of it like:

> *“This variable can only have values from this list.”*

---

## 🔹 Simple Example

```ts
enum Direction {
  Up,
  Down,
  Left,
  Right
}

let move: Direction;

move = Direction.Up;    // ✅ valid
move = Direction.Left;  // ✅ valid
// move = "Up";         // ❌ not allowed
```

---

## 🔹 Enum with Custom Values

```ts
enum Status {
  Success = "SUCCESS",
  Error = "ERROR",
  Loading = "LOADING"
}

let currentStatus: Status = Status.Success;
```

---

## 🌍 Real-World Use Cases

---

## 1️⃣ User Role (Authentication / Authorization)

```ts
enum Role {
  Admin = "ADMIN",
  User = "USER",
  Guest = "GUEST"
}

type User = {
  name: string;
  role: Role;
};

const user1: User = {
  name: "John",
  role: Role.Admin
};
```

✔ Prevents invalid roles like `"SuperAdmin"`

---

## 2️⃣ API Status Handling

```ts
enum ApiStatus {
  Idle,
  Loading,
  Success,
  Error
}

let apiState: ApiStatus = ApiStatus.Loading;
```

Used in **React / Angular**:

```ts
if (apiState === ApiStatus.Loading) {
  console.log("Fetching data...");
}
```

---

## 3️⃣ Order Status (E-commerce)

```ts
enum OrderStatus {
  Placed = "PLACED",
  Shipped = "SHIPPED",
  Delivered = "DELIVERED",
  Cancelled = "CANCELLED"
}

function trackOrder(status: OrderStatus) {
  console.log("Order is:", status);
}

trackOrder(OrderStatus.Shipped);
```

---

## 4️⃣ Payment Method

```ts
enum PaymentMethod {
  CreditCard,
  DebitCard,
  UPI,
  Cash
}

function pay(method: PaymentMethod) {
  console.log("Payment using", method);
}
```

---

## 🆚 Enum vs Union Type

Sometimes **union types** can replace enums:

```ts
type Status = "SUCCESS" | "ERROR" | "LOADING";
```

### When to use Enum?

✔ When values are **reused in many places**
✔ When values are **related logically**
✔ When you want **auto-completion & safety**

---

## ⭐ Key Benefits

✔ Prevents invalid values
✔ Improves code readability
✔ Easy to maintain
✔ Great for constants

---

### 🧠 One-line summary

> **Enum = predefined list of allowed values**

