# Index Signature 

An index signature tells TypeScript:

“This object can have any number of properties, and I know the type of their keys and values.”

It’s useful when you don’t know all the property names in advance.

### Index Signature in TypeScript (Short Note)

An **index signature** allows an object to have **dynamic keys** when you don’t know the property names in advance.

```ts
type Data = {
  [key: string]: number
}
```

* **Key type**: `string` (or `number`)
* **Value type**: `number`

#### Example

```ts
const scores: Data = {
  math: 90,
  english: 85
}
```

#### Use cases

* Dictionary / map-like objects
* API responses with unknown keys
* Dynamic configuration or settings

#### Important rule

All properties must match the index signature value type.

```ts
type User = {
  name: string
  age: number
  [key: string]: string | number
}
```

#### Alternative

```ts
type Data = Record<string, number>
```

**In one line:**
👉 *Index signature tells TypeScript what type of keys and values an object can have when keys are dynamic.*
