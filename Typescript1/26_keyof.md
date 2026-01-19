# keyod 

keyof is used to extract the keys of a Interface so that we cna have a list of keys and as a parameter we will accep only the correct key.


> **`keyof` takes an object type and gives you a union of its property names (keys). list of property**

---

## Basic idea 

If you have an object type with keys like `name`, `age`, and `email`,
then `keyof` means:

👉 “Give me all the allowed key names of this object.”

---

## Simple example

```ts
type Person = {
  name: string
  age: number
  isStudent: boolean
}
```

Now use `keyof`:

```ts
type PersonKeys = keyof Person
```

### What is `PersonKeys`?

```ts
// Same as:
type PersonKeys = "name" | "age" | "isStudent"
```

So `keyof` turns **object keys into string literal types**.

---

## Why is this useful?

It helps TypeScript **prevent mistakes** when working with object keys.

---

## Example: safer function

❌ Without `keyof` (unsafe)

```ts
function getValue(obj: any, key: string) {
  return obj[key]
}
```

You can pass **any string**, even invalid ones.

---

✅ With `keyof` (safe)

```ts
function getValue(obj: Person, key: keyof Person) {
  return obj[key]
}
```

Now TypeScript only allows valid keys:

```ts
getValue({ name: "Alex", age: 25, isStudent: true }, "name") // ✅
getValue({ name: "Alex", age: 25, isStudent: true }, "age")  // ✅
getValue({ name: "Alex", age: 25, isStudent: true }, "email") // ❌ Error
```

---


## One-line summary

> **`keyof` = “only allow valid property names of an object type.”**

