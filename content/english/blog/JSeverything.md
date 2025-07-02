---
title: " javaScript Everything"
meta_title: ""
description: "this is meta description"
date: 2025-05-02T05:00:00Z
image: "/images/JSproject1.png"
categories: ["Basic", "JavaScript"]
author: "Aditya Dhawle"
tags: ["JavaScript", "DOM"]
draft: false
---

# Complete JS Course Syllabus

### 📦 Chapter 1: Variables & Declarations

##### 🧠 What are Variables?

<p>
Variables are containers that hold data.
They help us store, reuse, and update information in JavaScript — from simple values like
numbers to complex data like arrays and objects.
Think of a variable as a box with a name on it. You can put something inside it (a value), and later
check or change what's inside.
In JavaScript, you create these boxes using keywords: var , let , or const .
</p>

<hr>

##### 🧪 var, let, and const – Line-by-Line Comparison
<hr>

##### 🧓 var – Old and risky
- Scoped to functions, not blocks
- Can be redeclared and reassigned
- Hoisted to the top with undefined value

```javascript
var score = 10;
var score = 20; // OK
```

#####   💻 let – Modern and safe
- Scoped to blocks ( {} )
- Can be reassigned but not redeclared
- Hoisted, but stays in the Temporal Dead Zone (TDZ)

```javascript
let age = 25;
age = 30; // ✅
let age = 40; // ❌ Error (same block)
```

##### 🔐 const – Constant values
- Scoped to blocks
- Cannot be reassigned or redeclared
- Value must be assigned at declaration
- TDZ applies here too
```javascript
const PI = 3.14;
PI = 3.14159; // ❌ Error
```
**👉 But: If const holds an object/array, you can still change its contents:**

```javascript
const student = { name: "Riya" };
student.name = "Priya"; // ✅ OK
student = {}; // ❌ Error

```


##### 🔥 Scope in Real Life
- Block Scope → Code inside {} like in loops, if , etc.
- Function Scope → Code inside a function
- let and const follow block scope
- var ignores block scope — which leads to bugs.

```javascript
{
 var x = 5;
 let y = 10;
 const z = 15;
}
console.log(x); // ✅ 5
console.log(y); // ❌ ReferenceError
console.log(z); // ❌ ReferenceError
```

##### 🧨 Hoisting

**JavaScript prepares memory before running code.It moves all declarations to the top — this is called hoisting.**

But:
- var is hoisted and set to undefined
- let and const are hoisted but not initialized — so accessing them early gives
ReferenceError

```javascript
console.log(a); // undefined
var a = 10;

```

```javascript
console.log(b); // ❌ ReferenceError
let b = 20;
```

##### ️ ⚠️Common Confusions (JS Reality Checks)

- const doesn't make things fully constant. It protects the variable, not the value
- var is outdated — it's better to use let and const .
- let and const behave similarly, but const gives more safety — use it when you're not
planning to reassign.


##### 🧠 Mindset Rule

**Use const by default. Use let only when you plan to change the value.Avoid var — it belongs to the past.**

##### 🧪 Practice Zone

1. Declare your name and city using const , and your age using let .
2. Try this and observe the result:
```javascript
let x = 5;
let x = 10;

```
3.  Guess the output:
```javascript
console.log(count);
var count = 42;
```
4. Create a const object and add a new key to it — does it work?
5. Try accessing a let variable before declaring it — what error do you see?
6. Change a const array by pushing a value. Will it throw an error?


### 🧠 Chapter 2: Data Types + Type System


##### 📦 What Are Data Types?

<p>In JavaScript, every value has a type.
These types define what kind of data is being stored — a number, text, boolean, object, etc.
There are two categories:</p>

- Primitive types – stored directly
- Reference types – stored as memory references.

##### 🔹 Primitive Data Types

1. **String → Text "hello" , 'Sheryians'**
2. **Number → Any numeric value 3 , -99 , 3.14**
3. **Boolean → True or false true , false**
4.  **Undefined → Variable declared but not assigned let x; → x is undefined**
5.  **Null → Intentional empty value let x = null;**
6.  **Symbol → Unique identifier (rarely used)**
7.  **. BigInt → Very large integers 123456789012345678901234567890n**

##### 🔹 Reference Data Types
- Object → { name: "Harsh", age: 26 }
- Array → [10, 20, 30]
- Function → function greet() {}
**These are not copied directly, but by reference.**

<hr>

##### 🔍 typeof Operator

**Used to check the data type of a value:**

```javascript
typeof "Sheryians" // "string"
typeof 99 // "number"
typeof true // "boolean"
typeof undefined // "undefined"
typeof null // "object" ← known bug
typeof [] // "object"
typeof {} // "object"
typeof function(){} // "function"
```
**Note: typeof null === "object" is a bug, but has existed since the early days of JS.**

##### 🔁 Type Coercion (Auto-Conversion)

**JavaScript auto-converts types in some operations:**

```javascript
"5" + 1 // "51" → number converted to string
"5" - 1 // 4 → string converted to number
true + 1 // 2
null + 1 // 1
undefined + 1 // NaN
```

##### 🚨 Loose vs Strict Equality

- == compares value with type conversion
- === compares value + type (no conversion)

```javascript
5 == "5" // true
5 === "5" // false
```
**Always prefer === for accurate comparisons**