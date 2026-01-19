# Type 
Its similar to Interface , we can but we can define number and string directly in it means we can define primitive types as well.
We can use Union with Type that we can not use with Interface to combine two interfaces.
We can use the extends with the Interface but not with the type.



## 🔹 `type`

* Similar to `interface`
* Can define **primitive types** (`string`, `number`, etc.)
* Can use **union (`|`)**
* Uses **intersection (`&`)** instead of `extends`

### Example: Primitive + Union (possible with `type`)

```ts
type ID = number | string;

type Status = "active" | "inactive";
```

❌ Not possible with `interface`

---

### Example: Union of object types

```ts
type Admin = {
  permissions: string[];
};

type User = {
  name: string;
};

type Account = Admin | User;
```

---

### Example: Combining types (Intersection)

```ts
type AdminUser = Admin & User;
```

---

## 🔹 `interface`

* Used mainly for **object shapes**
* Cannot define primitives
* Cannot use union (`|`)
* Uses **`extends`** for inheritance

### Example: Extending interfaces

```ts
interface User {
  name: string;
}

interface Admin extends User {
  permissions: string[];
}
```

✔ Cleaner for object inheritance
❌ Cannot do `Admin | User`

---

## 🆚 Quick Comparison (Union vs Extends)

### Union (`type`)

```ts
type Response = Success | Error;
```

### Extends (`interface`)

```ts
interface Success {
  data: string;
}

interface Error {
  message: string;
}
```

---

## 🧠 Summary Table

| Feature            | `type` | `interface` |   |
| ------------------ | ------ | ----------- | - |
| Primitive types    | ✅      | ❌           |   |
| Union (`           | `)     | ✅           | ❌ |
| Intersection (`&`) | ✅      | ❌           |   |
| `extends`          | ❌      | ✅           |   |
| Object inheritance | ⚠️     | ✅           |   |

---

### ⭐ One-line rule

> Use **`type`** for **unions & primitives**
> Use **`interface`** for **object extension & structure**

