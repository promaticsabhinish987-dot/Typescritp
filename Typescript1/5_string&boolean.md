

# String and Boolean Data Types in TypeScript

---

## 1. Applying String Data Type

**Definition:**
The `string` data type is used to store text values.

```ts
let name: string = "Alice";
```

**Ways to write strings:**

```ts
let s1: string = "Hello";     // Double quotes
let s2: string = 'World';     // Single quotes
let s3: string = `Hello TS`;  // Template string
```

---

## 2. Converting Values to String Data Type

### 2.1 Using `String()`

Converts any value into a string.

```ts
let num: number = 100;
let str: string = String(num);
```

---

### 2.2 Using `.toString()`

```ts
let value: number = 50;
let text: string = value.toString();
```

⚠️ **Confusing Case:**

```ts
let x = null;
x.toString(); // ❌ Error
```

✔ Safe way:

```ts
String(x); // "null"
```

---

### 2.3 Template Literals

```ts
let age: number = 20;
let message: string = `Age is ${age}`;
```

---

## 3. Applying Boolean Data Type

**Definition:**
The `boolean` data type stores logical values.

```ts
let isActive: boolean = true;
```

---

## 4. Possible Boolean Values

Only **two values** are allowed:

```ts
true
false
```

---

## 5. Boolean Inference and Declaration Issues

### 5.1 Type Inference

```ts
let isLoggedIn = true; // inferred as boolean
```

### 5.2 Declaration Issue (Confusing Case)

```ts
let flag: boolean = "true"; // ❌ Error
```

✔ Correct:

```ts
let flag: boolean = true;
```

---

### 5.3 Truthy and Falsy Confusion

```ts
Boolean(1);      // true
Boolean(0);      // false
Boolean("Hi");   // true
Boolean("");     // false
```

⚠️ These are **boolean conversions**, not boolean values themselves.

---

## 6. Converting Values to Boolean

```ts
Boolean(10);     // true
Boolean("");     // false
Boolean(null);   // false
```

---

## 7. Running TypeScript with HTML File

### Step 1: TypeScript File (`app.ts`)

```ts
let username: string = "John";
let isAdmin: boolean = false;

document.body.innerHTML = `
  <h1>${username}</h1>
  <p>Admin: ${isAdmin}</p>
`;
```

---

### Step 2: Compile TypeScript

```bash
tsc app.ts
```

---

### Step 3: HTML File (`index.html`)

```html
<!DOCTYPE html>
<html>
<head>
  <title>TS Demo</title>
</head>
<body>
  <script src="app.js"></script>
</body>
</html>
```

---

## 8. Confusing Code Examples Explained

### Example 1: String + Number

```ts
let result = "10" + 5; // "105"
```

➡ Number is converted to string automatically.

---

### Example 2: Boolean in String

```ts
let msg = "Value is " + true; // "Value is true"
```

---

### Example 3: Boolean from String

```ts
Boolean("false"); // true 😵
```

➡ Any non-empty string is `true`.

---

## 9. Best Practices

✔ Always use explicit types
✔ Use `String()` for safe string conversion
✔ Avoid mixing types blindly
✔ Use template literals for clarity
✔ Don’t confuse `"true"` with `true`

---

## 🔑 One-Line Summary

* **String** stores text data and supports multiple conversion methods
* **Boolean** stores true/false values and requires careful handling during conversion
* **TypeScript prevents type-related errors at compile time**

---


Just say 😊
