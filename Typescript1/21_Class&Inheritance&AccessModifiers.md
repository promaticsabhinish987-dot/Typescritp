
---

# 🔷 Class in TypeScript

### 📌 Definition (one line)

> A **class** is a blueprint used to create objects with properties and methods.

### Example

```ts
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log("Hello, my name is", this.name);
  }
}

const p1 = new Person("John", 25);
p1.greet();
```

---

# 🔐 Access Modifiers in TypeScript

### 📌 Definition (one line)

> **Access modifiers** control where class properties and methods can be accessed.

---

## 1️⃣ `public` (default)

> Accessible **everywhere**

```ts
class Car {
  public brand: string;

  constructor(brand: string) {
    this.brand = brand;
  }
}

const car = new Car("BMW");
console.log(car.brand); // ✅
```

---

## 2️⃣ `private`

> Accessible **only inside the same class**

```ts
class BankAccount {
  private balance: number = 0;

  deposit(amount: number) {
    this.balance += amount;
  }
}

const acc = new BankAccount();
// acc.balance = 100; ❌ Error
```

---

## 3️⃣ `protected`

> Accessible **inside class and child classes**

```ts
class Animal {
  protected type: string = "Animal";
}

class Dog extends Animal {
  bark() {
    console.log("This is a", this.type); // ✅
  }
}

const dog = new Dog();
// dog.type ❌ Error
```

---

# 🧬 Inheritance in TypeScript

### 📌 Definition (one line)

> **Inheritance** allows a class to acquire properties and methods of another class.

---

### Example

```ts
class Employee {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  work() {
    console.log(this.name, "is working");
  }
}

class Manager extends Employee {
  manage() {
    console.log(this.name, "is managing the team");
  }
}

const m1 = new Manager("Alice");
m1.work();
m1.manage();
```

---

# 🧠 Summary Table

| Concept     | One-line meaning                 |
| ----------- | -------------------------------- |
| Class       | Blueprint for objects            |
| public      | Accessible everywhere            |
| private     | Accessible only inside class     |
| protected   | Accessible in class & subclasses |
| Inheritance | Child class reuses parent class  |

---

### ⭐ One-line takeaway

> **Classes define structure, access modifiers protect data, and inheritance promotes code reuse.**



# 🧬 Inheritance with `super` in TypeScript

### 📌 One-line definition

> **Inheritance** allows a child class to use the properties and methods of a parent class using `extends`, and `super` is used to access the parent class.

---

## 🔹 Basic Example

```ts
class Person {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  greet() {
    console.log("Hello, I am", this.name);
  }
}

class Student extends Person {
  grade: number;

  constructor(name: string, grade: number) {
    super(name); // calls Parent constructor
    this.grade = grade;
  }

  study() {
    console.log(this.name, "is studying in grade", this.grade);
  }
}

const s1 = new Student("John", 10);
s1.greet();
s1.study();
```

---

## 🔹 Why `super` is needed

### 1️⃣ `super()` – call parent constructor

* Must be called **before using `this`**
* Initializes parent class properties

```ts
super(name);
```

❌ Without `super()` → Error

---

### 2️⃣ `super.method()` – call parent method

```ts
class Teacher extends Person {
  greet() {
    super.greet(); // call parent method
    console.log("I am a teacher");
  }
}

const t1 = new Teacher("Alice");
t1.greet();
```

---

## 🔹 Real-World Example

```ts
class Vehicle {
  start() {
    console.log("Vehicle started");
  }
}

class Car extends Vehicle {
  start() {
    super.start();
    console.log("Car is ready to drive");
  }
}

const myCar = new Car();
myCar.start();
```

---

## 🧠 Key Rules to Remember

✔ `extends` → inherit parent class
✔ `super()` → call parent constructor
✔ `super.method()` → call parent method
✔ `super()` must be first in constructor

---

### ⭐ One-line takeaway

> **`super` connects child classes to their parent class, enabling reuse and extension of functionality.**

me 👍

