

---

# Number Data Type in TypeScript — Short Note

### 1. Basic Declaration and Initialization

**Definition:** A number variable is declared using the `number` type to store numeric values.

```ts
let age: number = 25;
```

---

### 2. Integer Numbers

**Definition:** Integers are whole numbers without decimal points.

```ts
let count: number = 100;
```

---

### 3. Floating-Point Numbers

**Definition:** Floating-point numbers contain decimal values.

```ts
let price: number = 99.99;
```

---

### 4. Binary Numbers

**Definition:** Binary numbers use base-2 and start with `0b`.

```ts
let binaryNum: number = 0b1010; // 10
```

---

### 5. Hexadecimal Numbers

**Definition:** Hexadecimal numbers use base-16 and start with `0x`.

```ts
let hexNum: number = 0x1f; // 31
```

---

### 6. Type Inference with Numbers

**Definition:** TypeScript automatically detects the type when a value is assigned.

```ts
let score = 90; // inferred as number
```

---

### 7. Redeclare Issue

**Definition:** A variable declared with `let` cannot be redeclared in the same scope.

```ts
let marks: number = 80;
let marks: number = 90; // ❌ Error
```

---

### 8. How to Add Numbers with Data Type

**Definition:** Arithmetic operations work only when both operands are numbers.

```ts
let a: number = 10;
let b: number = 20;
let sum: number = a + b;
```

---

### 9. Convert String to Number

**Definition:** Strings can be converted to numbers using built-in methods.

```ts
let str: string = "123";
let num: number = Number(str);
```

Other methods:

```ts
parseInt("10");
parseFloat("10.5");
```

---

### 10. Potential Pitfalls

**Definition:** Errors can occur due to type mismatch, precision issues, or invalid conversions.

```ts
let result = 0.1 + 0.2; // 0.30000000000000004
```

---

### 11. Best Practices

**Definition:** Following safe rules improves accuracy and avoids runtime errors.

✔ Use `number` only for numeric values
✔ Check for `NaN` before calculations
✔ Avoid very large numbers
✔ Use `bigint` for large integers

```ts
if (Number.isNaN(num)) {
  console.log("Invalid number");
}
```

---

### 🔑 One-Line Summary

**The `number` data type in TypeScript is used to store all numeric values, supports multiple number formats, provides type safety, and requires careful handling to avoid precision and conversion errors.**

---
