---
title: " javaScript Everything"
meta_title: ""
description: "this is meta description"
date: 2025-05-02T05:00:00Z
image: "/images/3.png"
categories: ["Basic", "JavaScript"]
author: "Aditya Dhawle"
tags: ["JavaScript", "DOM"]
draft: true
---

# Complete JavaScript Syllabus

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

  {{< quiztab title="Q1: 🧠 Basics" >}}
  {{< quiz id="q1" question="What is the purpose of variables in JavaScript?" answer="To store and manage data values" options="To style HTML||To store and manage data values||To repeat loops||To create databases" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q2: var keyword" >}}
  {{< quiz id="q2" question="Which statement about 'var' is TRUE?" answer="It is function-scoped and can be redeclared" options="It is block-scoped||It cannot be redeclared||It is function-scoped and can be redeclared||It throws ReferenceError when accessed early" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q3: let keyword" >}}
  {{< quiz id="q3" question="What happens when you try to redeclare a 'let' variable in the same block?" answer="It throws a SyntaxError" options="It overwrites silently||It throws a SyntaxError||It gets hoisted as undefined||It becomes a const" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q4: const keyword" >}}
  {{< quiz id="q4" question="Which is TRUE about 'const'?" answer="It must be assigned a value at declaration" options="It can be reassigned||It must be assigned a value at declaration||It can be declared without assignment||It is not hoisted" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q5: const & objects" >}}
  {{< quiz id="q5" question="Can a const object be modified?" answer="Yes, its properties can be changed" options="No, const makes it immutable||Yes, its properties can be changed||Only if it’s frozen||It depends on scope" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q6: Scope" >}}
  {{< quiz id="q6" question="Which variable is accessible outside the block?" answer="Only var" options="let and const||Only var||All of them||None of them" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q7: Hoisting var" >}}
  {{< quiz id="q7" question="What is printed when you access a var before its declaration?" answer="undefined" options="ReferenceError||NaN||null||undefined" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q8: Hoisting let" >}}
  {{< quiz id="q8" question="Accessing a let variable before it's declared results in:" answer="ReferenceError due to TDZ" options="undefined||null||ReferenceError due to TDZ||It works fine" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q9: Reassignment" >}}
  {{< quiz id="q9" question="What happens if you try to reassign a const variable?" answer="It throws a TypeError" options="It works fine||It throws a SyntaxError||It throws a TypeError||It becomes undefined" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q10: Best Practices" >}}
  {{< quiz id="q10" question="What is the recommended mindset when using variables?" answer="Use const by default, let only when needed" options="Always use var||Use const by default, let only when needed||Only use let||Avoid const" >}}
  {{< /quiztab >}}

{{< /quiztabs >}}


  {{< sqads >}}



### 🧠 Chapter 2: Data Types + Type System




##### 📦 What Are Data Types?




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

{{< quiztabs >}}

  {{< quiztab title="Q1: Primitive Type" >}}
  {{< quiz id="q1" question="What is the type of 'Hello' in JavaScript?" answer="string" options="text||character||string||word" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q2: Reference Type" >}}
  {{< quiz id="q2" question="Which of the following is a reference type in JavaScript?" answer="Array" options="Boolean||Number||String||Array" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q3: typeof null" >}}
  {{< quiz id="q3" question="What does typeof null return?" answer="object" options="null||undefined||object||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q4: typeof function" >}}
  {{< quiz id="q4" question="What is the typeof a function?" answer="function" options="object||function||method||callback" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q5: Type Coercion" >}}
  {{< quiz id="q5" question="What is the result of '5' + 1 in JavaScript?" answer="51" options="6||51||error||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q6: Boolean Coercion" >}}
  {{< quiz id="q6" question="What is the result of true + 1?" answer="2" options="true1||11||2||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q7: Equality" >}}
  {{< quiz id="q7" question="What does 5 == '5' return?" answer="true" options="false||true||undefined||TypeError" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q8: Strict Equality" >}}
  {{< quiz id="q8" question="What does 5 === '5' return?" answer="false" options="true||false||undefined||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q9: Truthy & Falsy" >}}
  {{< quiz id="q9" question="Which of these is a falsy value in JavaScript?" answer="0" options="[]||{}||'false'||0" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q10: NaN Type" >}}
  {{< quiz id="q10" question="What is the typeof NaN?" answer="number" options="NaN||undefined||error||number" >}}
  {{< /quiztab >}}

{{< /quiztabs >}}

 {{< sqads >}}

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

{{< quiztabs >}}

  {{< quiztab title="Q1: Arithmetic ➕" >}}
  {{< quiz id="q1" question="What is the result of 10 % 3?" answer="1" options="0||1||3||10" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q2: Exponentiation **" >}}
  {{< quiz id="q2" question="What does 2 ** 3 evaluate to?" answer="8" options="6||9||8||23" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q3: Assignment += " >}}
  {{< quiz id="q3" question="What is the final value of score if score = 5; score += 2;" answer="7" options="5||2||10||7" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q4: Comparison ==" >}}
  {{< quiz id="q4" question="What does 5 == '5' return?" answer="true" options="false||true||error||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q5: Comparison ===" >}}
  {{< quiz id="q5" question="What does 5 === '5' return?" answer="false" options="false||true||undefined||error" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q6: Logical AND" >}}
  {{< quiz id="q6" question="What is the result of true && false?" answer="false" options="true||false||undefined||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q7: Logical OR" >}}
  {{< quiz id="q7" question="What is the result of false || true?" answer="true" options="false||true||undefined||null" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q8: Logical NOT" >}}
  {{< quiz id="q8" question="What does !true return?" answer="false" options="false||true||0||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q9: typeof undefined" >}}
  {{< quiz id="q9" question="What is typeof undefined?" answer="undefined" options="null||object||undefined||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q10: typeof null" >}}
  {{< quiz id="q10" question="What is typeof null?" answer="object" options="null||undefined||object||NaN" >}}
  {{< /quiztab >}}

 

  {{< quiztab title="Q12: Pre vs Post Increment" >}}
  {{< quiz id="q12" question="Which one returns the value before incrementing?" answer="i++" options="++i||i++||i+1||post-i" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q13: Ternary Operator" >}}
  {{< quiz id="q13" question="What is returned by: (5 > 3) ? 'Yes' : 'No'?" answer="Yes" options="No||Yes||undefined||error" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q14: typeof function" >}}
  {{< quiz id="q14" question="What is typeof function(){} in JS?" answer="function" options="object||method||function||callback" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q15: Confusion - '5' - 1" >}}
  {{< quiz id="q15" question="What is the result of '5' - 1?" answer="4" options="51||NaN||error||4" >}}
  {{< /quiztab >}}

{{< /quiztabs >}}


 {{< sqads >}}

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


{{< quiztabs >}}

  {{< quiztab title="Q1: If Block" >}}
  {{< quiz id="q1" question="Which block runs if the condition in 'if' is true?" answer="The code inside the if block" options="All blocks||Only else||None||The code inside the if block" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q2: else if Order" >}}
  {{< quiz id="q2" question="In an else if chain, which condition gets checked first?" answer="The one written first from the top" options="Random||Last one||The one written first from the top||The one with highest value" >}}
  {{< /quiztab >}}

  

  {{< quiztab title="Q4: else block" >}}
  {{< quiz id="q4" question="When does the else block run?" answer="When all other conditions fail" options="Always||When all other conditions fail||When if is true||At random" >}}
  {{< /quiztab >}}

  

  {{< quiztab title="Q6: switch default" >}}
  {{< quiz id="q6" question="What does the default case in switch do?" answer="Runs when no case matches" options="Runs always||Runs when no case matches||Runs if first case fails||Runs before all cases" >}}
  {{< /quiztab >}}

 

 

  {{< quiztab title="Q9: Early Return Benefit" >}}
  {{< quiz id="q9" question="Why is early return used in functions?" answer="To exit early and keep code clean" options="To crash the app||To delay execution||To exit early and keep code clean||To skip compilation" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q10: Common Confusion" >}}
  {{< quiz id="q10" question="What’s a common bug with switch-case statements?" answer="Forgetting to use break, causing multiple cases to run" options="Using == in case||Forgetting to use break, causing multiple cases to run||Missing default||Using variables inside cases" >}}
  {{< /quiztab >}}

{{< /quiztabs >}}

 {{< sqads >}}

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

{{< quiztabs >}}

  {{< quiztab title="Q1: Why Loops?" >}}
  {{< quiz id="q1" question="What is the primary purpose of loops?" answer="To repeat code without writing it again" options="To create variables||To break code||To repeat code without writing it again||To define conditions" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q2: for loop start" >}}
  {{< quiz id="q2" question="In a for loop, what usually happens first?" answer="Initialization" options="Condition check||Increment||Initialization||Return" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q3: for loop condition" >}}
  {{< quiz id="q3" question="What does the condition in a for loop do?" answer="Checks if loop should continue" options="Increments the variable||Defines output||Checks if loop should continue||Breaks the loop" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q4: while loop check" >}}
  {{< quiz id="q4" question="When is the condition checked in a while loop?" answer="Before each iteration" options="Only at start||At the end||Before each iteration||Never" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q5: do-while guarantee" >}}
  {{< quiz id="q5" question="What’s unique about do-while loops?" answer="They run at least once" options="They are faster||They run at least once||They never end||They don’t use conditions" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q6: Output Check" >}}
  {{< quiz id="q6" question="What will this print?\nfor(let i=0;i<3;i++) { console.log(i); }" answer="0 1 2" options="0 1 2 3||0 1 2||1 2 3||0 1" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q7: Infinite Loop Risk" >}}
  {{< quiz id="q7" question="What causes an infinite loop?" answer="Condition never becomes false" options="Using let||Missing console.log||Condition never becomes false||No increment used" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q8: break keyword" >}}
  {{< quiz id="q8" question="What does the break keyword do?" answer="Stops the loop immediately" options="Skips to next loop||Restarts the loop||Stops the loop immediately||Pauses the loop" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q9: continue keyword" >}}
  {{< quiz id="q9" question="What does the continue keyword do?" answer="Skips current iteration" options="Ends loop||Skips current iteration||Repeats last value||Inverts condition" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q10: continue output" >}}
  {{< quiz id="q10" question="What gets printed?\nfor(let i=1; i<=3; i++) {\n if(i==2) continue;\n console.log(i);\n}" answer="1 3" options="1 2 3||1 3||2||1 2" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q11: for-of use" >}}
  {{< quiz id="q11" question="What can for-of loop iterate over?" answer="Arrays and strings" options="Only numbers||Only objects||Arrays and strings||Only strings" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q12: for-in use" >}}
  {{< quiz id="q12" question="Which is the best use for for-in loop?" answer="Iterating keys in an object" options="Looping arrays||Increment counters||Iterating keys in an object||Math operations" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q13: forEach vs for" >}}
  {{< quiz id="q13" question="What’s a key limitation of forEach?" answer="It doesn’t allow break or continue" options="It’s slower||Can’t print||It doesn’t allow break or continue||Only works with strings" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q14: do-while edge case" >}}
  {{< quiz id="q14" question="What will do-while run if the condition is false initially?" answer="Still runs once" options="Never runs||Gives error||Still runs once||Runs twice" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q15: forEach syntax" >}}
  {{< quiz id="q15" question="What argument does forEach provide to the callback?" answer="Each array item" options="The loop count||Each object key||Each array item||The array length" >}}
  {{< /quiztab >}}

  

  {{< quiztab title="Q17: for-in on array" >}}
  {{< quiz id="q17" question="Why is using for-in on arrays not recommended?" answer="It may access unexpected keys" options="It’s slower||It doesn’t work||It may access unexpected keys||Arrays are not iterable" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q18: Real Use" >}}
  {{< quiz id="q18" question="Which loop is best when you don't know how many times you'll run?" answer="while or do-while" options="for||forEach||for-in||while or do-while" >}}
  {{< /quiztab >}}

{{< /quiztabs >}}


 {{< sqads >}}

### 🧮 Chapter 6: Functions

##### 🧠 What are Functions?
<p>Functions are blocks of reusable logic.
Instead of repeating the same task again and again, wrap it in a function and reuse it with
different inputs.
</p>

**Think of a function like a vending machine:**
- Input: you give money + item code
- Output: it gives you the item
- Logic: hidden inside


##### 🛠 Function Declarations
```javascript
function greet() {
 console.log("Welcome to Sheryians!");
}
greet();

```
**You define it once, then call it whenever needed.**

##### 🧾 Parameters vs Arguments
```javascript
function greet(name) {
 console.log("Hello " + name);
}
greet("Harsh");

```
- name is a parameter
- "Harsh" is the argument you pass

##### 🌀 Return Values
```javascript
function sum(a, b) {
 return a + b;
}
let total = sum(5, 10); // total is 15

```
- return sends back a result to wherever the function was called
- After return , function exits


##### 🧰 Function Expressions
```javascript
const greet = function () {
 console.log("Hello!");
};

```
- Functions stored in variables
- Cannot be hoisted (you canʼt call them before theyʼre defined)

##### 🏹 Arrow Functions
```javascript
const greet = () => {
 console.log("Hi!");
};
```
- Cleaner syntax

- No own this , no arguments object


##### 🧂 Default + Rest + Spread
```javascript
unction multiply(a = 1, b = 1) {
 return a * b;
}
function sum(...nums) {
 return nums.reduce((acc, val) => acc + val, 0);
}
let nums = [1, 2, 3];
console.log(sum(...nums)); // Spread
```

- a = 1 → default parameter
- ...nums → rest parameter
- ...nums (in call) → spread operator


##### 🎯 First-Class Functions
**JavaScript treats functions as values:**
- Assign to variables
- Pass as arguments
- Return from other functions

```javascript
function shout(msg) {
 return msg.toUpperCase();
}
function processMessage(fn) {
 console.log(fn("hello"));
}
processMessage(shout);

```

##### 🧠 Higher-Order Functions (HOF)

**Functions that accept other functions or return functions.**
```javascript
nction createMultiplier(x) {
 return function (y) {
 return x * y;
 };
}
let double = createMultiplier(2);
console.log(double(5)); // 10

```

##### 🔐 Closures & Lexical Scope

**Closures = when a function remembers its parent scope, even after the parent has finished.**
```javascript
function outer() {
 let count = 0;
 return function () {
 count++;
 console.log(count);
 };
}
let counter = outer();
counter(); // 1
counter(); // 2

```
**Even after outer is done, counter still remembers count .**

<hr>

##### ⚡ IIFE – Immediately Invoked Function Expression

```javascript
(function () {
 console.log("Runs immediately");
})();
```
**Used to create private scope instantly**


##### 🚀 Hoisting: Declarations vs Expressions

```javascript
hello(); // works
function hello() {
 console.log("Hi");
}
greet(); // error
const greet = function () {
 console.log("Hi");
};
```
- Declarations are hoisted
- Expressions are not

##### ️ ️Common Confusions
- Arrow functions donʼt have their own this
- You canʼt break out of forEach
- Closures often trap old variable values
- Return vs console.log – don't mix them up

##### ️ ️🧠 Mindset
<p>Functions are your logic blocks + memory holders (via closure).
They keep your code clean, DRY, and reusable.
</p>


{{< quiztabs >}}

  {{< quiztab title="Q1: Function Purpose" >}}
  {{< quiz id="q1" question="Why do we use functions in JavaScript?" answer="To reuse blocks of logic with different inputs" options="To store data||To display HTML||To reuse blocks of logic with different inputs||To define loops" >}}
  {{< /quiztab >}}

 

  {{< quiztab title="Q3: Parameters vs Arguments" >}}
  {{< quiz id="q3" question="In function greet(name), what is 'name'?" answer="Parameter" options="Argument||Parameter||Return||Scope" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q4: Return Statement" >}}
  {{< quiz id="q4" question="What does the return keyword do?" answer="Sends a value back and exits the function" options="Prints value||Pauses function||Sends a value back and exits the function||Rewrites variables" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q5: Function Expression" >}}
  {{< quiz id="q5" question="Why can't you call a function expression before it's defined?" answer="Because it's not hoisted" options="Because it's private||Because it's async||Because it's not hoisted||Because it has no name" >}}
  {{< /quiztab >}}



  {{< quiztab title="Q7: Default Parameter" >}}
  {{< quiz id="q7" question="What is the default value of b in: function add(a, b = 5)?" answer="5" options="undefined||5||null||NaN" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q8: Rest Operator" >}}
  {{< quiz id="q8" question="What does ...nums do in function sum(...nums)?" answer="Collects multiple arguments into an array" options="Spreads array into numbers||Skips arguments||Collects multiple arguments into an array||Assigns default value" >}}
  {{< /quiztab >}}



  {{< quiztab title="Q10: First-Class Function" >}}
  {{< quiz id="q10" question="What makes functions first-class in JS?" answer="They can be passed, returned, and assigned like values" options="They are global||They only run once||They store state||They can be passed, returned, and assigned like values" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q11: Higher-Order Function" >}}
  {{< quiz id="q11" question="What is a Higher-Order Function?" answer="A function that accepts or returns another function" options="A function with more arguments||A function with return||A function that accepts or returns another function||A big function" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q12: Closure Meaning" >}}
  {{< quiz id="q12" question="What is a Closure in JavaScript?" answer="A function remembering variables from its outer scope" options="A sealed block||A loop function||A function remembering variables from its outer scope||A constant value" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q13: Closure Example" >}}
  {{< quiz id="q13" question="In this code, what keeps 'count' remembered?\nfunction outer() {\n let count = 0;\n return function() {\n count++;\n console.log(count);\n };\n}" answer="Closure" options="Parameter||Global||Closure||Loop" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q14: IIFE Purpose" >}}
  {{< quiz id="q14" question="Why use an IIFE (Immediately Invoked Function Expression)?" answer="To run code immediately and create private scope" options="To call later||To delay logic||To run code immediately and create private scope||To define a class" >}}
  {{< /quiztab >}}

 {{< /quiztabs >}}


 {{< sqads >}}

### 🧰 Chapter 7: Arrays

##### 🧠 What is an Array?
<p>An array is like a row of boxes, where each box holds a value and has an index (0, 1, 2…).
Arrays help you store multiple values in a single variable — numbers, strings, or even
objects/functions.
</p>
```javascript
let fruits = ["apple", "banana", "mango"];
```

##### 🏗 Creating & Accessing Arrays

```javascript
let marks = [90, 85, 78];
console.log(marks[1]); // 85
marks[2] = 80; // Update index 2
```
- Indexing starts from 0
- You can access, update, or overwrite values by index

##### ️ Common Array Methods
```javascript

```
###### 🧱 Modifiers (Change original array)
```javascript
let arr = [1, 2, 3, 4];
arr.push(5); // Add to end
arr.pop(); // Remove last
arr.shift(); // Remove first
arr.unshift(0); // Add to start
arr.splice(1, 2); // Remove 2 items starting at index 1
arr.reverse(); // Reverse order

```

###### 🔍 Extractors (Don't modify original array)
```javascript
let newArr = arr.slice(1, 3); // Copy from index 1 to 2
arr.sort(); // Lexical sort by default
```


##### 🔄 Iteration Methods
map()
**Returns a new array with modified values.**
```javascript
let prices = [100, 200, 300];
let taxed = prices.map(p => p * 1.18);
```
filter()
Filters out elements based on a condition.

```javascript
let nums = [1, 2, 3, 4];
let even = nums.filter(n => n % 2 === 0);
```
reduce()
Reduces the array to a single value.

```javascript
let total = nums.reduce((acc, val) => acc + val, 0);
```
forEach()
Performs an action for each element (but returns undefined).

```javascript
nums.forEach(n => console.log(n));
```
find(), some(), every()

```javascript
nums.find(n => n > 2); // First match
nums.some(n => n > 5); // At least one true
nums.every(n => n > 0); // All true
```

##### ️ Destructuring & Spread
```javascript
let [first, second] = ["a", "b", "c"];
let newArr = [...nums, 99]; // Spread to copy & add
```



{{< quiztabs >}}

  {{< quiztab title="Q1: Array Basics" >}}
  {{< quiz id="q1" question="What is an array in JavaScript?" answer="A collection of values stored at numeric indexes" options="A function group||A loop type||A collection of values stored at numeric indexes||An object with key-values" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q2: Index Start" >}}
  {{< quiz id="q2" question="What index does a JavaScript array start at?" answer="0" options="1||0||-1||Depends on the value" >}}
  {{< /quiztab >}}

  

  {{< quiztab title="Q4: push method" >}}
  {{< quiz id="q4" question="What does arr.push(5) do?" answer="Adds 5 to the end of the array" options="Adds 5 to start||Removes 5||Adds 5 to the end of the array||Sorts the array" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q5: pop method" >}}
  {{< quiz id="q5" question="What does arr.pop() do?" answer="Removes last element from array" options="Removes first element||Adds last element||Removes last element from array||Duplicates last element" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q6: shift method" >}}
  {{< quiz id="q6" question="What does arr.shift() remove?" answer="First element" options="Last element||Middle element||First element||Every odd value" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q7: unshift method" >}}
  {{< quiz id="q7" question="Which method adds to the beginning of an array?" answer="unshift()" options="push()||pop()||unshift()||reverse()" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q8: splice method" >}}
  {{< quiz id="q8" question="What does arr.splice(1,2) do?" answer="Removes 2 elements starting at index 1" options="Adds 2 elements||Replaces all items||Removes 2 elements starting at index 1||Splits array in half" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q9: reverse method" >}}
  {{< quiz id="q9" question="Which method reverses the array order?" answer="reverse()" options="sort()||slice()||reverse()||map()" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q10: slice method" >}}
  {{< quiz id="q10" question="What does arr.slice(1,3) return?" answer="Elements from index 1 to 2" options="Full array||Index 1 to 3||Elements from index 1 to 2||First 3 items" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q11: map method" >}}
  {{< quiz id="q11" question="What does map() return?" answer="A new array with modified values" options="Same array||Nothing||Total sum||A new array with modified values" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q12: filter method" >}}
  {{< quiz id="q12" question="What is filter() used for?" answer="Getting values that match a condition" options="Looping all values||Adding elements||Getting values that match a condition||Sorting elements" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q13: reduce result" >}}
  {{< quiz id="q13" question="What does reduce() return?" answer="A single value (accumulated)" options="An object||An array||A string||A single value (accumulated)" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q14: forEach vs map" >}}
  {{< quiz id="q14" question="What’s the key difference between forEach and map?" answer="forEach returns undefined, map returns new array" options="map is faster||forEach runs once||forEach returns undefined, map returns new array||map changes original" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q15: find method" >}}
  {{< quiz id="q15" question="What does find() return?" answer="First matching element" options="Index of match||Every match||First matching element||Last matching element" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q16: some method" >}}
  {{< quiz id="q16" question="What does some() return?" answer="true if at least one element matches" options="true if all match||false always||true if at least one element matches||false if empty" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q17: every method" >}}
  {{< quiz id="q17" question="What does every() check for?" answer="If all elements pass the test" options="If one passes||If none pass||If all elements pass the test||If array is empty" >}}
  {{< /quiztab >}}

  

  {{< quiztab title="Q19: Spread Operator" >}}
  {{< quiz id="q19" question="What does [...arr, 10] do?" answer="Creates new array with arr values + 10 at end" options="Adds 10 to each||Copies first 10||Creates new array with arr values + 10 at end||Multiplies by 10" >}}
  {{< /quiztab >}}

  {{< quiztab title="Q20: Array Confusion" >}}
  {{< quiz id="q20" question="Which method mutates the original array?" answer="splice()" options="map()||filter()||slice()||splice()" >}}
  {{< /quiztab >}}

 {{< /quiztabs >}}

 {{< sqads >}}

### 🧱 Chapter 8: Objects

##### 🧠 What is an Object?
<p>Objects in JavaScript are like real-world records – a collection of key-value pairs.
They help us store structured data (like a student, a product, or a user profile).</p>

```javascript
let student = {
 name: "Ravi",
 age: 21,
 isEnrolled: true
};

```

##### 🔑 Key-Value Structure
- Keys are always strings (even if you write them as numbers or identifiers)

- Values can be anything – string, number, array, object, function, etc.
```javascript
console.log(student["name"]); // Ravi
console.log(student.age); // 21

```
##### 📍 Dot vs Bracket Notation
- Use dot notation for fixed key names

- Use bracket notation for dynamic or multi-word keys
```javascript
student["full name"] = "Ravi Kumar"; // ✅
student.course = "JavaScript"; // ✅
```

##### 🏗 Nesting and Deep Access
Objects can have nested objects (objects inside objects)

```javascript
let user = {
 name: "Amit",
 address: {
 city: "Delhi",
 pincode: 110001
 }
};
console.log(user.address.city); // Delhi
```
##### ️ Object Destructuring
You can extract values directly:
```javascript
let { name, age } = student;
```
For nested objects:

```javascript
let {
 address: { city }
} = user;

```

  
##### 🔁 Looping Through Objects
for-in loop
```javascript
for (let key in student) {
 console.log(key, student[key]);
}
```
Object.keys(), Object.values(), Object.entries()

```javascript
Object.keys(student); // ["name", "age", "isEnrolled"]
Object.entries(student); // [["name", "Ravi"], ["age", 21], ...]

```

##### 📦 Copying Objects
Shallow Copy (one level deep)

```javascript
let newStudent = { ...student };
let newOne = Object.assign({}, student);

```
Deep Copy (nested levels)

```javascript
let deepCopy = JSON.parse(JSON.stringify(user)); 

```
**❗ Note: JSON-based copy works only for plain data (no functions, undefined, etc.)**

##### ❓ Optional Chaining
Avoids errors if a nested property is undefined:
```javascript
console.log(user?.address?.city); // Delhi
console.log(user?.profile?.email); // undefined (no error)

```

##### 🧠 Computed Properties
You can use variables as keys:
```javascript
let key = "marks";
let report = {
 [key]: 89
};

```

##### ️ Common Confusions
- Shallow copy copies only the first level
- for-in includes inherited keys (be cautious!)
- delete obj.key removes the property
- Spread ≠ deep copy


##### ️ 🧠 Mindset
<p>Objects are structured state – perfect for modeling anything complex: a user, a form, a product,
etc.
Use destructuring, chaining, and dynamic keys wisely.
</p>


{{< quiztabs >}}

{{< quiztab title="Q1: Object Basics" >}}
{{< quiz id="q1" question="What is the basic structure of a JavaScript object?" answer="Key-value pairs" options="Index-based values||Key-value pairs||String only||Single values" >}}
{{< /quiztab >}}

{{< quiztab title="Q2: Key Type" >}}
{{< quiz id="q2" question="What type are keys in JavaScript objects?" answer="Strings" options="Numbers||Booleans||Strings||Functions" >}}
{{< /quiztab >}}

{{< quiztab title="Q3: Value Type" >}}
{{< quiz id="q3" question="What types can values in an object be?" answer="Any type" options="Only string||Only number||Only object||Any type" >}}
{{< /quiztab >}}





{{< quiztab title="Q6: When to Use Brackets" >}}
{{< quiz id="q6" question="When is bracket notation required?" answer="For dynamic or multi-word keys" options="Always||For booleans||For arrays||For dynamic or multi-word keys" >}}
{{< /quiztab >}}







{{< quiztab title="Q11: for-in Usage" >}}
{{< quiz id="q11" question="What does for-in loop iterate over in objects?" answer="Keys" options="Values only||Functions||Indexes||Keys" >}}
{{< /quiztab >}}

{{< quiztab title="Q12: Object.keys()" >}}
{{< quiz id="q12" question="What does Object.keys(obj) return?" answer="An array of keys" options="A string||Only first key||An array of keys||A boolean" >}}
{{< /quiztab >}}

{{< quiztab title="Q13: Object.entries()" >}}
{{< quiz id="q13" question="What does Object.entries(obj) return?" answer="Array of [key, value] pairs" options="Only keys||Only values||Array of [key, value] pairs||Nested object" >}}
{{< /quiztab >}}

{{< quiztab title="Q14: Copy Object (Shallow)" >}}
{{< quiz id="q14" question="Which method copies an object shallowly?" answer="...spread or Object.assign()" options="JSON.stringify||== operator||...spread or Object.assign()||filter()" >}}
{{< /quiztab >}}

{{< quiztab title="Q15: Deep Copy Limitation" >}}
{{< quiz id="q15" question="What can JSON deep copy NOT handle?" answer="Functions and undefined values" options="Strings||Numbers||Objects||Functions and undefined values" >}}
{{< /quiztab >}}







{{< quiztab title="Q19: Object Type Check" >}}
{{< quiz id="q19" question="What does typeof {} return?" answer="object" options="array||object||function||null" >}}
{{< /quiztab >}}

{{< quiztab title="Q20: Object vs Array" >}}
{{< quiz id="q20" question="How to check if a value is an array?" answer="Array.isArray(value)" options="value == array||typeof array||Array.isArray(value)||object instanceof array" >}}
{{< /quiztab >}}





{{< quiztab title="Q23: Spread Confusion" >}}
{{< quiz id="q23" question="Does spread operator create a deep copy?" answer="No, only shallow copy" options="Yes||No, only shallow copy||Partially||Only if inside array" >}}
{{< /quiztab >}}

{{< quiztab title="Q24: Object.assign()" >}}
{{< quiz id="q24" question="What does Object.assign({}, obj) do?" answer="Creates a shallow copy of obj" options="Deletes keys||Sorts object||Creates a shallow copy of obj||Converts object to string" >}}
{{< /quiztab >}}

{{< quiztab title="Q25: Object Clarity" >}}
{{< quiz id="q25" question="Which is NOT true about JS objects?" answer="They preserve order of keys strictly" options="They store key-value pairs||Keys are strings||They preserve order of keys strictly||They support nested data" >}}
{{< /quiztab >}}

{{< /quiztabs >}}

 {{< sqads >}}