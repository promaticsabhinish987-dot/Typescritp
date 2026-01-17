# Data Types in TS

1. Primitive Types
2. Object Types
3. Special Types
4. Advanced Types
5. Function Types

## 1. Primitive Types

1. Number
2. String
3. Boolean
4. Null
5. Undefined
6. BigInt
7. Symbol

## 2. Object Ypes

1. Array
2. Tuple
3. Object

## 3. Special Types

1. Any
2. Unknown
3. Void
4. Never


## 4. Advanced Types

1. Union
2. Intersaction
3. Type Alias
4. Enum
5. Literal Types

## 5. Function Types


---

# Data Types in TypeScript

## 1. Primitive Types

* **Number** – Used to store numeric values.

  ```ts
  let age: number = 25;
  ```

* **String** – Used to store text data.

  ```ts
  let name: string = "TypeScript";
  ```

* **Boolean** – Used to store true or false values.

  ```ts
  let isActive: boolean = true;
  ```

* **Null** – Represents an intentional empty value.

  ```ts
  let result: null = null;
  ```

* **Undefined** – Represents a variable that has not been assigned a value.

  ```ts
  let value: undefined = undefined;
  ```

* **BigInt** – Used to store very large numbers.

  ```ts
  let bigNumber: bigint = 12345678901234567890n;
  ```

* **Symbol** – Used to create unique identifiers.

  ```ts
  let id: symbol = Symbol("id");
  ```

---

## 2. Object Types

* **Array** – Used to store multiple values of the same type.

  ```ts
  let numbers: number[] = [1, 2, 3];
  ```

* **Tuple** – Used to store fixed-length arrays with specific types.

  ```ts
  let user: [string, number] = ["Alice", 30];
  ```

* **Object** – Used to store structured data with key–value pairs.

  ```ts
  let person: { name: string; age: number } = { name: "Bob", age: 25 };
  ```

---

## 3. Special Types

* **Any** – Allows any type of value (disables type checking).

  ```ts
  let data: any = "hello";
  ```

* **Unknown** – Similar to `any` but safer and requires type checking.

  ```ts
  let value: unknown = 10;
  ```

* **Void** – Used when a function does not return any value.

  ```ts
  function logMessage(): void { console.log("Hello"); }
  ```

* **Never** – Used for functions that never return (e.g., errors or infinite loops).

  ```ts
  function throwError(): never { throw new Error("Error"); }
  ```

---

## 4. Advanced Types

* **Union** – Allows a variable to hold more than one type.

  ```ts
  let id: number | string = 101;
  ```

* **Intersection** – Combines multiple types into one.

  ```ts
  type A = { a: number }; type B = { b: string }; let obj: A & B = { a: 1, b: "x" };
  ```

* **Type Alias** – Creates a custom name for a type.

  ```ts
  type User = { name: string; age: number };
  ```

* **Enum** – Used to define a set of named constants.

  ```ts
  enum Direction { Up, Down, Left, Right }
  ```

* **Literal Types** – Allows exact values as types. you can store only these 2 values.

  ```ts
  let status: "success" | "error" = "success";
  ```

---

## 5. Function Types

* **Function Type** – Defines parameter and return types of a function.

  ```ts
  let add: (a: number, b: number) => number = (x, y) => x + y;
  ```

---

