
---

# 🎯 What are Decorators in TypeScript?

**In easy language:**

> A **decorator** is a special function that **adds extra behavior** to a class, method, property, or parameter **without changing its code**.

Think of it like a **wrapper** or **annotation**.

---

## 🔔 Important before using decorators

Decorators are **experimental** in TypeScript.

Enable them in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "experimentalDecorators": true
  }
}
```

---

# 🧱 Types of Decorators (quick view)

* Class Decorator
* Method Decorator
* Property Decorator
* Parameter Decorator

We’ll focus on **method decorators** for override.

---

# 🧪 Basic Decorator Example

```ts
function Log(target: any) {
  console.log("Class created")
}

@Log
class User {}
```

When the class is loaded, `"Class created"` is logged.

---

# 🛠️ Method Decorator (Core concept)

```ts
function LogMethod(
  target: any,
  propertyKey: string,
  descriptor: PropertyDescriptor
) {
  console.log(`Method name: ${propertyKey}`)
}
```

---

# 🔁 Override Function Using a Decorator

### Goal:

Override a method **without modifying the original code**

---

## ✅ Example: Override method behavior

```ts
function OverrideLog(
  target: any,
  propertyKey: string,
  descriptor: PropertyDescriptor
) {
  const originalMethod = descriptor.value

  descriptor.value = function (...args: any[]) {
    console.log("Before method call")

    const result = originalMethod.apply(this, args)

    console.log("After method call")
    return result
  }
}
```

---

## 🔹 Use the decorator

```ts
class Calculator {
  @OverrideLog
  add(a: number, b: number) {
    return a + b
  }
}
```

---

## ▶️ Output

```ts
const calc = new Calculator()
calc.add(2, 3)
```

Console:

```text
Before method call
After method call
```

The method is **overridden (wrapped)** by the decorator.

---

# 🏢 Real-World Use Cases

### 1️⃣ Logging

```ts
@LogExecution
saveData() {}
```

### 2️⃣ Authorization

```ts
@AdminOnly
deleteUser() {}
```

### 3️⃣ Performance tracking

```ts
@MeasureTime
loadData() {}
```

### 4️⃣ Validation

```ts
@ValidateInput
submitForm(data)
```

---

# ⚠️ Important Notes

* Decorators run **when class is defined**, not when instantiated
* Method decorators can **replace or modify functions**
* Decorators are mostly used in **Angular**, **NestJS**

---

# 🧠 One-line summary

> **Decorators add or override behavior without touching the original code.**

> **Override via decorator = wrapping the original function and changing its behavior.**

---

