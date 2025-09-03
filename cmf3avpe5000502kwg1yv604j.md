---
title: "Introduction to functions in Javascript"
datePublished: Wed Sep 03 2025 01:30:19 GMT+0000 (Coordinated Universal Time)
cuid: cmf3avpe5000502kwg1yv604j
slug: introduction-to-functions-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/mM9vVJ2oDeI/upload/0e985c343f60ea057d255a90943c6eaf.jpeg
tags: programming-blogs, javascript, alexandrecalaca

---

> Functions are one of the most important concepts in JavaScript. They allow us to organize code, avoid repetition, and make programs easier to maintain.

## Introduction

### What’s a Function?

A function is a block of code designed to perform a specific task. Instead of writing the same instructions multiple times, you can group them into a function and call it whenever you need.

Let’s break it down in a very simple way: a function is a piece of code that you’d like to use many times. Instead of writing that piece of code over and over again, you create a function. Then, whenever you need it, you simply call or invoke the function.

**Key terms:**

* **Function** → A block of code.
    
* **Invoke/Call** → Run the function.
    

**Example:**

```plaintext
function sayHello() {
  console.log("Hello, world!");
}

sayHello(); // Function call
```

---

## 🔹 2. Parameters and Arguments

Functions can receive input values.

* **Parameters** → Placeholders in the function definition.
    
* **Arguments** → Real values passed when calling the function.
    

**Example:**

```plaintext
function greet(name) { // "name" is the parameter
  console.log("Hello, " + name + "!");
}

greet("Alice");   // "Alice" is the argument
greet("Bob");     // "Bob" is the argument
```

---

## 🔹 3. Return Values

Functions can produce and return results using the keyword `return`.

* Without `return`, functions only perform actions.
    
* With `return`, they can give back a value to be reused.
    

**Example:**

```plaintext
function add(a, b) {
  return a + b;
}

let result = add(5, 3);
console.log(result); // 8
```

---

## 🔹 4. Reusability (Avoiding Repetition)

One of the main reasons for using functions is to avoid repeating code.

**Without a function:**

```plaintext
console.log("Hello, Alice!");
console.log("Hello, Bob!");
console.log("Hello, Charlie!");
```

**With a function:**

```plaintext
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet("Alice");
greet("Bob");
greet("Charlie");
```

✔️ Easier to maintain, more organized.

---

## 🔹 5. Function Expressions

Functions can also be stored inside variables. This is called a **function expression**.

**Example:**

```plaintext
const multiply = function(x, y) {
  return x * y;
};

console.log(multiply(2, 4)); // 8
```

---

## 🔹 6. Arrow Functions

JavaScript provides a shorter syntax for functions, called **arrow functions**.

* Often used for simple one-line functions.
    

**Example:**

```plaintext
const square = (n) => n * n;

console.log(square(6)); // 36
```

---

## 🔹 7. Functions in Real Use

Functions are everywhere in JavaScript, for example, when working with arrays or handling events.

**Example with arrays:**

```plaintext
let numbers = [1, 2, 3, 4];
let doubled = numbers.map(num => num * 2);

console.log(doubled); // [2, 4, 6, 8]
```

**Example with events:**

```plaintext
document.querySelector("button").onclick = function() {
  alert("Button clicked!");
};
```

---

### Recap of Key Terms

* **Function** → Block of code.
    
* **Call/Invoke** → Run the function.
    
* **Parameters** → Inputs defined in the function.
    
* **Arguments** → Real values passed when calling.
    
* **Return** → Sends a value back.
    
* **Function Expression** → Function stored in a variable.
    
* **Arrow Function** → Short syntax for writing functions.
    

---

## Practice

Practice your knowledge with the following exercises:

* Function that prints your name.
    
* Function that doubles a number.
    
* Function that squares a number.
    
* Arrow function that checks if a number is even.
    
* Mini-project: Calculate rectangle area.
    

---