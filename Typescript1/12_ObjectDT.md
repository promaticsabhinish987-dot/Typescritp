
---

# 📌 Object Data Type in TypeScript

### 🔹 Definition (One line)

**An object is a collection of key–value pairs where each key maps to a value of a specific data type.**

---

## ✅ Basic Typed Object

```ts
let person: {
  name: string;
  age: number|undefined;
} = {
  name: "Alice",
  age: 25
};
```

### Access properties

```ts
console.log(person.name);
```

---

## ➕ How to Add Key–Value Pairs

### ❌ Error (property not defined)

```ts
person.city = "London"; // ❌
```

### ✅ Use Optional Property

```ts
let person: {
  name: string;
  age: number;
  city?: string;
} = {
  name: "Alice",
  age: 25
};

person.city = "London"; // ✅
```

---

## 🔁 Dynamic Keys (Index Signature)

```ts
let data: {
  [key: string]: string | number|undefined;
} = {};

data.username = "admin";
data.id = 101;
```

---

## 🔒 Readonly Object

```ts
let person: {
  readonly name: string;
  readonly age: number;
} = {
  name: "Alice",
  age: 25
};

person.age = 30; // ❌ Error
```

---

# 📌 Nested Objects in TypeScript

### 🔹 Definition (One line)

**A nested object is an object that contains another object as a property.**

---

## ✅ Nested Object Example

```ts
let employee: {
  id: number;
  name: string;
  address: {
    street: string;
    city: string;
    pincode: number;
  };
address2:{
//we can put any value here
}
} = {
  id: 1,
  name: "John",
  address: {
    street: "MG Road",
    city: "Bangalore",
    pincode: 560001
  }
};
```

---

## 🔍 Access Nested Properties

```ts
console.log(employee.address.city); // Bangalore
```

---

## ➕ Add Property Inside Nested Object

### ❌ Error (not defined)

```ts
employee.address.country = "India"; // ❌
```

### ✅ Make it Optional

```ts
let employee: {
  id: number;
  name: string;
  address: {
    street: string;
    city: string;
    pincode: number;
    country?: string;
  };
} = {
  id: 1,
  name: "John",
  address: {
    street: "MG Road",
    city: "Bangalore",
    pincode: 560001
  }
};

employee.address.country = "India"; // ✅
```

---

## 🔁 Dynamic Nested Object

```ts
let config: {
  settings: {
    [key: string]: string | boolean;
  };
} = {
  settings: {}
};

config.settings.theme = "dark";
config.settings.isAdmin = true;
```

---

## 🔒 Readonly Nested Object

```ts
let employee: {
  readonly id: number;
  readonly address: {
    readonly city: string;
  };
} = {
  id: 1,
  address: {
    city: "Delhi"
  }
};

employee.address.city = "Mumbai"; // ❌
```

---

## 🆚 Flat Object vs Nested Object

| Feature     | Flat Object  | Nested Object           |
| ----------- | ------------ | ----------------------- |
| Structure   | Single level | Multiple levels         |
| Readability | Simple       | More detailed           |
| Use Case    | Small data   | Complex real-world data |

---

## ✅ Best Practices

* Use **nested objects** for real-world models
* Prefer **explicit typing** over `object`
* Use `readonly` for immutable data
* Use `optional (?)` properties for flexibility
* Use **index signatures** for dynamic keys

---

