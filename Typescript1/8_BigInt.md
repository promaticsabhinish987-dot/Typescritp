
---

# BigInt in TypeScript

---

## 1. Problem with the `number` Data Type

**Issue:**
The `number` type in JavaScript/TypeScript cannot safely represent very large integers.It shows unexprected behaviour. In js and ts we have a Max safe integer, which is 2^53-1, beyond this limit precision issues arises.

```ts
let x: number = 9007199254740991; // MAX_SAFE_INTEGER
let y: number = x + 1;
console.log(y); // ❌ Wrong result
```

📌 **Reason:**
`number` uses **64-bit floating-point representation**, which causes **precision loss** for large integers.

```ts
Number.MAX_SAFE_INTEGER; // 9007199254740991
```

Any integer beyond this is **unsafe**.

---

## 2. What Is `bigint`?

**Definition:**
`bigint` is a data type used to store **very large integers** without losing precision.

👉 It was introduced to solve the precision problem of `number`.

---

## 3. How to Create and Declare BigInt

### Method 1: Using `n` suffix (most common)

```ts
let bigNumber: bigint = 12345678901234567890n;
```

---

### Method 2: Using `BigInt()` constructor

```ts
let bigValue: bigint = BigInt("12345678901234567890");
```

⚠️ Cannot pass decimal values:

```ts
BigInt(10.5); // ❌ Error
```

---

## 4. Performing Arithmetic Operations with BigInt

BigInt supports **basic arithmetic operations**.

```ts
let a: bigint = 10n;
let b: bigint = 20n;

let sum = a + b;   // 30n
let diff = b - a;  // 10n
let prod = a * b;  // 200n
let div = b / a;   // 2n
```

⚠️ **Important Rule:**
BigInt **cannot be mixed** with `number`.

```ts
let result = 10n + 5; // ❌ Error
```

✔ Correct:

```ts
let result = 10n + BigInt(5);
```

---

## 5. Comparison with Number

```ts
10n === 10; // false
10n == 10;  // true (not recommended)
```

✔ Always use strict comparison (`===`).

---

## 6. Limitations of BigInt

❌ No decimals allowed
❌ Cannot be used with `Math` functions
❌ Cannot be mixed directly with `number`
❌ Not supported in very old browsers

---

## 7. Potential Use Cases of BigInt in TypeScript

✔ Handling **large database IDs**
✔ Financial calculations with **huge integers**
✔ Cryptography and security systems
✔ Blockchain and smart contracts
✔ Scientific calculations requiring precision

---

## 8. When to Use `number` vs `bigint`

| Use Case              | Recommended Type |
| --------------------- | ---------------- |
| Normal calculations   | `number`         |
| Decimal values        | `number`         |
| Very large integers   | `bigint`         |
| IDs beyond safe limit | `bigint`         |

---

## 🔑 One-Line Summary

**`bigint` is used in TypeScript to safely handle very large integers that exceed the limits of the `number` data type, ensuring accurate calculations without precision loss.**

---
