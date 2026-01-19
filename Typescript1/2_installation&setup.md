
---

## Installation & Setup of TypeScript

**Note:**
Browsers do not understand TypeScript directly. Therefore, TypeScript code must first be **converted (compiled) into JavaScript** before it can run in the browser or in Node.js.

---

## Steps to Set Up TypeScript

1. Install **Node.js** on your system.
2. Install **TypeScript** (either locally or globally).
3. Create a file with the **`.ts`** extension.
4. Use the TypeScript compiler to generate a **JavaScript (.js)** file.

---

## Installing TypeScript

TypeScript can be installed in **two ways**:

### 1. Local Installation (Recommended for projects)

This installs TypeScript only for a specific project.

```javascript
npm install typescript --save-dev
```

---

### 2. Global Installation

This installs TypeScript for the entire system and can be used anywhere.

```javascript
npm install -g typescript
```

---

## How to Run a TypeScript File

To compile a TypeScript file and automatically watch for changes, use:

```javascript
npx tsc app.ts --watch
```

This command:

* Converts `app.ts` into `app.js`
* Automatically recompiles the file whenever changes are made

---

This setup allows developers to write TypeScript code and run it as JavaScript smoothly and efficiently.


Note :- npx is important to use for running tsc compiler if you have installed typescript as dev dependency.
