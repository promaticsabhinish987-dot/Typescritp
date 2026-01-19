

## 1️⃣ What is a Generic in TypeScript?

A **generic** allows you to write a function, class, or interface that works with **multiple types** **while preserving type safety**.


```ts
function fruit(name: number|string|boolean): number|string|boolean {
    return name;
}
```
or

```ts
function fruit<T>(name: T): T {
    return name;
}
```

### What’s happening here?

* `T` is a **type variable**
* TypeScript infers `T` from the argument you pass
* The **return type is the same as the input type**

### Usage

```ts
const apple = fruit("apple");   // T = string
const hundred = fruit(100);     // T = number
const boo = fruit(true);        // T = boolean
```

TypeScript infers types automatically:

```ts
apple.toUpperCase();   // ✅ allowed
hundred.toFixed(2);    // ✅ allowed
boo.valueOf();         // ✅ allowed
```

This is **compile-time type safety**.

---

## 2️⃣ Why Generics Are Important

Generics:

* Preserve the **relationship between input and output types**
* Prevent **type-related runtime bugs**
* Give **better IntelliSense & autocomplete**
* Avoid unnecessary type casting

---

## 3️⃣ Problem with `any`

Your `any` example:  any doesnt allow the type check and the returned value type will also be any.

```ts
function fruit2(name: any): any {
    return name;
}
```

### What goes wrong?

```ts
const result = fruit2("apple");

result.toUpperCase(); // ✅ compiles
result.toFixed(2);    // ❌ runtime error (but TypeScript allows it)
```

⚠️ TypeScript **disables type checking** when `any` is used.

---
