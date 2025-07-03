---
title: " javaScript Everything"
meta_title: ""
description: "this is meta description"
date: 2025-05-02T05:00:00Z
image: "/images/3.png"
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



{{< quiztabs >}}

  {{< quiztab title="Easy 💡" >}}

  {{< quiz id="q1" question="What is the full form of HTML?" answer="HyperText Markup Language" options="HighText Markdown Language||HyperText Markup Language||Home Tool Markup Language||Hyper Trainer Marking Language" >}}



  {{< /quiztab >}}


  {{< quiztab title="Medium 🧠" >}}

  {{< quiz id="q3" question="What does typeof null return in JS?" answer="object" options="null||undefined||object||NaN" >}}

  {{< quiz id="q4" question="Which function converts JSON to object?" answer="JSON.parse()" options="JSON.parse()||JSON.stringify()||parse.JSON()||convert.json()" >}}

  {{< /quiztab >}}


  {{< quiztab title="Hard 🔥" >}}

  {{< quiz id="q5" question="What is output of 2 + '2'?" answer="22" options="4||22||'4'||undefined" >}}

  {{< quiz id="q6" question="Best way to declare constant in JS?" answer="const" options="var||let||const||define" >}}

  {{< /quiztab >}}

{{< /quiztabs >}}

{{< sqads >}}



### 🧠 Chapter 2: Data Types + Type System

{{< inarticlead >}}



##### 📦 What Are Data Types?


{{< adsense >}}


<p>In JavaScript, every value has a type.
These types define what kind of data is being stored — a number, text, boolean, object, etc.
There are two categories:</p>

- Primitive types – stored directly
- Reference types – stored as memory references.

##### 🔹 Primitive Data Types

1. **String → Text "hello" , 'Aditya'**
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
typeof "Your Name" // "string"
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


##### NaN – Not a Number

```javascript
typeof NaN // "number"
```
<p>Even though it means “Not a Number”, NaN is actually of type number .
This is because operations like 0 / 0 or parseInt("abc") still produce a numeric result —
just an invalid one.
</p>


##### 🔦 Truthy and Falsy Values

<b>Falsy values:</b>

**false , 0 , "" , null , undefined , NaN**
<b>Everything else is truthy, including:</b>
**"0" , "false" , [] , {} , function(){}**


##### Practice Zone


### 🔄 Chapter 3: Operators
##### 🔧 What are Operators?

<p>Operators are special symbols or keywords in JavaScript used to perform operations on values
(operands).
Youʼll use them in calculations, comparisons, logic, assignments, and even type checks.
Think of them as the verbs of your code — they act on data.
</p>

##### ➕ Arithmetic Operators

Used for basic math.


```javascript
+ // addition
- // subtraction
* // multiplication
/ // division
% // modulus (remainder)
** // exponentiation (power)
```

Example:

```javascript
let a = 10, b = 3;
console.log(a + b); // 13
console.log(a % b); // 1
console.log(2 ** 3); // 8
```

##### 🧮 Assignment Operators
 Assign values to variables.

 ```javascript
= // assigns value
+= // a += b => a = a + b
-= // a -= b
*=, /=, %=
 ```

Example:

```javascript
let score = 5;
score += 2; // score = 7
```

##### 🧾 Comparison Operators

```javascript
== // equal (loose)
=== // equal (strict – value + type)
!= // not equal (loose)
!== // not equal (strict)
> < >= <=
```

Example:
```javascript
console.log(5 == "5"); // true
console.log(5 === "5"); // false
```

##### ✅ Logical Operators
Used to combine multiple conditions

```javascript
&& // AND – both must be true
|| // OR – either one true
! // NOT – negates truthiness
```
Example:

```javascript
let age = 20, hasID = true;
if (age >= 18 && hasID) {
 console.log("Allowed");
}
```

##### 🌀 Unary Operators
Used on a single operand.


```javascript
+ // tries to convert to number
- // negates
++ // increment
-- // decrement
typeof // returns data type

```

Example:

```javascript
let x = "5";
console.log(+x); // 5 (converted to number)
```
##### ❓ Ternary Operator (Conditional)
Shorthand for if...else


```javascript
condition ? valueIfTrue : valueIfFalse
```

Example:

```javascript
let score = 80;
let grade = score > 50 ? "Pass" : "Fail";

```
##### 🧪 typeof Operator

```javascript
typeof 123 // "number"
typeof "hi" // "string"
typeof null // "object" (JS bug)
typeof [] // "object"
typeof {} // "object"
typeof function(){} // "function"
```

##### 🧠 Mindset

<p>Operators make logic happen.
They help you make decisions, combine values, and create expressions.
Try to:</p>

- Use === instead of == to avoid type bugs.
- se ternary for quick decisions, not complex ones
- Think in truthy/falsy when using && , || , ! .

##### ❓ Common Confusions
- "5" + 1 is "51" (string concat), but "5" - 1 is 4 (number subtract)

- !!value is a quick trick to convert anything into a boolean

- Pre-increment ( ++i ) vs post-increment ( i++ ) return different results



### 🧭 Chapter 4: Control Flow


##### 🚦 What is Control Flow?
<p>Control flow decides which code runs, when it runs, and how many times it runs.
It's like decision-making + direction in your JavaScript program.
If operators are the verbs, control flow is the traffic signal.
</p>

##### 🧱 if, else if, else

```javascript
if (condition) {
 // runs if condition is true
} else if (anotherCondition) {
 // runs if first was false, second is true
} else {
 // runs if none are true
}

```
✅ Example:

```javascript
if (condition) {
 // runs if condition is true
} else if (anotherCondition) {
 // runs if first was false, second is true
} else {
 // runs if none are true
}

```


##### 🌀 switch-case
Great for checking one variable against many values

```javascript
switch (value) {
 case value1:
 // code
 break;
 case value2:
 // code
 break;
 default:
 // fallback
}

```
Example:
```javascript
let fruit = "apple";
switch (fruit) {
 case "banana":
 console.log("Yellow");
 break;
 case "apple":
 console.log("Red");
 break;
 default:
 console.log("Unknown");
}

```
##### 🔁 Early Return Pattern

Used in functions to exit early if some condition fails.

```javascript
function checkAge(age) {
 if (age < 18) return "Denied";
 return "Allowed";
}

```

This avoids deep nesting and makes logic cleaner.

<hr>

##### ️ Common Confusions
- switch-case executes all cases after a match unless you break
- else if chain works top-down — order matters

- You can use truthy/falsy values directly in if


##### 🧠 Mindset
<p>Control flow = conditional storytelling.
It helps your program make choices and respond differently to different inputs.
Write readable branches. Avoid nesting too deep — use early return if needed</p>


### 🔁 Chapter 5: Loops

##### 🔄 Why Loops?
<p>Loops help us repeat code without rewriting it.
If a task needs to be done multiple times (e.g., printing 1–10, going through an array, or
checking each character in a string), loops are the backbone.
</p>

##### 🔁 for Loop

```javascript
for (let i = 0; i < 5; i++) {
 console.log(i);
}

```
- Start from i = 0
- Run till i < 5
- Increase i each time

##### 🔁 while Loop
```javascript
let i = 0;
while (i < 5) {
 console.log(i);
 i++;
}

```

##### 🔁 do-while Loop
```javascript
let i = 0;
do {
 console.log(i);
 i++;
} while (i < 5);

```
- Runs at least once, even if condition is false

##### ⛔ break and continue
- break : Exit loop completely
- continue : Skip current iteration and move to next
```javascript
for (let i = 1; i <= 5; i++) {
 if (i === 3) continue;
 console.log(i); // Skips 3
}
``` 

##### 🌀 for-of – Arrays & Strings
```javascript
for (let char of "Sheryians") {
 console.log(char);
}
```
- Works on anything iterable (arrays, strings)


##### 🧱 forEach – Arrays
```javascript
let nums = [10, 20, 30];
nums.forEach((num) => {
 console.log(num);
});
```
- Cleaner than for for arrays, but you canʼt break/return

##### 🧱 for-in – Objects (and arrays if needed)
```javascript
let user = { name: "Harsh", age: 26 };
for (let key in user) {
 console.log(key, user[key]);
}
```
- Goes over keys in objects


##### ️ Common Confusions
- for-in is for objects, not arrays (may cause issues with unexpected keys)
- forEach can't use break or continue
- while and do-while work best when number of iterations is unknown

##### 🧠 Mindset

### 🧮 Chapter 6: Functions

##### 🧠 What are Functions?

##### 🛠 Function Declarations
```javascript

```

##### 🧾 Parameters vs Arguments
```javascript

```
##### 🌀 Return Values
```javascript

```
##### 🧰 Function Expressions
```javascript

```

##### 🏹 Arrow Functions
```javascript

```

##### 🧂 Default + Rest + Spread
```javascript

```

##### 🎯 First-Class Functions
```javascript

```

##### 🧠 Higher-Order Functions (HOF)
```javascript

```

##### 🔐 Closures & Lexical Scope
```javascript

```

##### ⚡ IIFE – Immediately Invoked Function Expression

```javascript

```
##### 🚀 Hoisting: Declarations vs Expressions

```javascript

```

##### ️ ️Common Confusions
##### ️ ️🧠 Mindset


### 🧰 Chapter 7: Arrays

##### 🧠 What is an Array?
##### 🏗 Creating & Accessing Arrays
```javascript

```
##### ️ Common Array Methods
```javascript

```
###### 🧱 Modifiers (Change original array)
```javascript

```

###### 🔍 Extractors (Don't modify original array)
```javascript

```


##### 🔄 Iteration Methods
```javascript

```
##### ️ Destructuring & Spread
```javascript

```

##### ⚠️ Common Confusions
```javascript

```

### 🧱 Chapter 8: Objects

##### 🧠 What is an Object?

##### 🔑 Key-Value Structure
```javascript

```
##### 📍 Dot vs Bracket Notation
```javascript

```

##### 🏗 Nesting and Deep Access
```javascript

```
##### ️ Object Destructuring
```javascript

```

  
##### 🔁 Looping Through Objects
```javascript

```

##### 📦 Copying Objects
```javascript

```

##### ❓ Optional Chaining
```javascript

```

##### 🧠 Computed Properties
```javascript

```

##### ️ Common Confusions
```javascript

```

##### ️ 🧠 Mindset



