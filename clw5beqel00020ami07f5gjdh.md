---
title: "Understand Closures in Ruby once and for All"
datePublished: Mon May 13 2024 18:46:14 GMT+0000 (Coordinated Universal Time)
cuid: clw5beqel00020ami07f5gjdh
slug: understand-closures-in-ruby-once-and-for-all
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/OIohXAQ_lRw/upload/3c334648bd79ca89b963e0b6b30e1e8a.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## Introduction

### Closures in programming

Closures, a fundamental concept in programming, are like powerful mini-programs encapsulated within others.

They bring a unique capability to capture and remember the environment in which they were created, allowing them to retain access to variables even after the original function has finished executing.

It's as if they carry a piece of their birthplace with them, creating a dynamic link between different parts of your code.

> Remember this: They bring a unique capability to capture and remember the environment in which they were created.

---

### Importance in Ruby

In the Ruby world, closures take on special significance. They are not just code snippets; they're flexible entities that enhance the language's expressiveness.

By understanding closures, you gain the ability to create more robust and modular code, providing a bridge between simplicity and complexity.

Let's dive in!

---

## Basic of closures

### Definition

At its core, a closure is like a programming wizard that captures not just instructions but also the magical environment in which it was born.

In simpler terms, it's a bundled-up piece of code that remembers where it came from. Imagine it as a recipe that not only tells you what to cook but also keeps a memory of the kitchen it was written in.

---

### **Closures capture their surrounding environment**

Picture a closure as a traveler collecting souvenirs from each place it visits. Similarly, closures remember variables and conditions from the space where they were created.

This ability to capture the environment makes them adaptable and versatile, like a handy toolkit always ready for action.

Remember what we said at the beginning:

> They bring a unique capability to capture and remember the environment in which they were created.

---

### Closures and functions in Ruby

In Ruby, functions and closures share a close-knit relationship. Think of functions as the main actors on the coding stage, and closures as their trusty sidekicks.

Closures add a layer of flexibility to functions, allowing them to carry around specific knowledge from their origin. It's like giving functions a memory boost, making them smarter and more context-aware.

> Closures work on the top of Ruby functions.

---

## Closures with blocks in Ruby

### Create closures

In Ruby, think of blocks as the paintbrushes of closures. These are little sections of code that you can easily slot into your programs. It's like having a toolkit with customizable tools that adapt to different tasks.

Blocks, when combined with closures, bring a dynamic touch to your code, allowing you to encapsulate functionality in a neat package.

---

### With a simple block

```javascript
puts '#' * 10 + ' Understand closures ' + '#' * 10

def create_closure(x)
  # This block is an example of a closure
  ->(y) { x + y }
end

closure = create_closure(10)
puts closure.call(15)
puts closure.call(20)
```

Let's take a closer look:

* create\_closure(x)
    
    A method `create_closure` is defined, which takes a parameter `x`
    
* \-&gt;(y) { x + y }
    
    This Ruby lambda takes a parameter `y` and and returns the sum of x and y. The key point here is that the lambda captures the variable x from the surrounding scope, making it a closure.
    
* closure = create\_closure(10)
    
    It invokes the `create_closure` method, and the returned lambda is assigned to the variable `closure`. The closure effectively "remembers" the value of x from the enclosing scope, which is 10 in this case.
    
* puts [closure.call](http://closure.call)(15)
    
    When `closure.call(15)` is executed, it adds the captured x (which is 10) to the provided argument 15, resulting in 25
    
* puts closure.call(20)
    
    Similarly, `closure.call(20)` results in 30 because the captured `x` (still 10) is added to the argument 20
    

---

### Capturing variables

Picture a block as a little detective within your code, capturing specific variables and keeping them in its evidence bag.

When you create a closure using a block, it captures not just the code within the block but also the variables it references.

It's like the closure saying, "I'll take these ingredients with me wherever I go." This captured set of ingredients becomes part of the closure's toolkit, ensuring it has what it needs, no matter where it's invoked in your program.

---

## Closures with lambdas and procs in Ruby

### Introduction

Lambdas and Procs, like siblings in the Ruby family, are special kinds of closures. They share the ability to encapsulate functionality and carry a piece of the code environment with them.

Think of them as versatile tools in your programming toolkit, each with its unique characteristics. While they share similarities, understanding their differences allows you to choose the right tool for the task at hand.

---

### Syntax

The syntax for creating Lambdas and Procs is quite similar; they are both defined using `->`

```javascript
# Lambda syntax
my_lambda = ->(arg1, arg2) { puts arg1 + arg2 }

# Proc syntax
my_proc = Proc.new { |arg1, arg2| puts arg1 + arg2 }
```

---

### Basic differences

Lambdas are strict about the number of arguments they receive, behaving like well-disciplined sous-chefs.

On the other hand, Procs are more lenient, accepting any number of arguments and showing a bit more flexibility, like a laid-back friend who adapts to the situation.

---

### Lambda example

```javascript
puts "\n" + '#' * 10 + ' Closures with lambdas ' + '#' * 10

multiply_by_two = ->(x) { x * 2 }
puts multiply_by_two.call(5)
puts multiply_by_two.call(15)
```

Brief explanation

\-&gt;(x) { x \* 2 }:

Here, a lambda named multiply\_by\_two is created. This lambda takes one parameter x and returns the result of multiplying x by 2.

puts multiply\_by\_[two.call](http://two.call)(5): This line calls the lambda multiply\_by\_two with the argument 5 and prints the result. It should output 10 since 5 \* 2 is 10.

puts multiply\_by\_[two.call](http://two.call)(15): Similarly, this line calls the lambda with the argument 15 and prints the result. It should output 30 since 15 \* 2 is 30.

---

### Proc example

```javascript
puts "\n" + '#' * 10 + ' Closures with procs ' + '#' * 10

add_three = Proc.new { |num| num + 3 }
puts add_three.call(7)
puts add_three.call(15)
```

Brief explanation

* add\_three = [Proc.new](http://Proc.new) { |num| num + 3 }:
    
    a Proc named add\_three is created. This proc takes one parameter num and returns the result of adding 3 to it.
    
* puts add\_[three.call](http://three.call)(7):
    
    This line calls the proc add\_three with the argument 7 and prints the result. It should output 10 since 7 + 3 is 10.
    
* puts add\_[three.call](http://three.call)(15):
    
    Similarly, this line calls the proc with the argument 15 and prints the result. It should output 18 since 15 + 3 is 18.
    

---

## Scope and lifetime

### Variable scope

In Ruby, variable scope refers to the region of the code where a variable is accessible and can be modified.

Closures, being encapsulated blocks of code, have their own scope. When a closure is defined, it captures not only the code but also the scope of the variables at that moment.

This means the closure can access and manipulate variables from its enclosing scope, creating a self-contained environment.

---

### Lifetime

The lifetime of a closure in Ruby is not tied to the lifespan of its defining function. Once a closure is created, it exists independently of the function that gave birth to it.

Closures persist beyond the execution of their outer function, allowing them to be invoked and interacted with even after the surrounding code has completed its execution.

This longevity makes closures versatile tools with a lasting impact on program execution.

---

### Closures and their access

Closures in Ruby exhibit a concept known as "lexical scoping." Lexical scoping means that a closure retains access to the variables from its defining context.

Even when the outer function completes its execution, the closure maintains a reference to the environment it was created in.

This ensures that the closure can still access and modify variables from its original scope, providing a mechanism for persistent data encapsulation and manipulation.

---

## Common pitfalls and best practices

### Potential issues

Closures, while powerful, come with their own set of potential pitfalls. One common challenge is related to variable scope. If not handled carefully, closures might capture unintended variables or face scope-related issues, leading to unexpected behavior.

Another pitfall is the modification of captured variables outside the closure, potentially introducing bugs and making code harder to reason about. Understanding the nuances of closure scope and variable access is crucial to avoid unintentional side effects.

---

### Best practices

To harness the full potential of closures in Ruby, it's essential to follow some best practices. First and foremost, be mindful of variable scope. Explicitly declare variables within the closure or use parameters to pass values, avoiding unintended closures that capture variables from outer scopes.

Additionally, embrace clarity by keeping closures concise and focused on a specific task. This not only improves readability but also reduces the chances of unintended side effects.

Another best practice involves using closures for their intended purpose—encapsulation. Leverage closures to encapsulate and abstract functionality, creating modular and reusable code blocks.

When modifying captured variables, consider using local variables within the closure or employing functional programming principles like immutability to enhance predictability.

Lastly, strive for clarity in naming. Choose descriptive names for closures and their parameters, making it easier for others (and future you) to understand the purpose and functionality of the closure.

---

## Done

---

### Celebrate

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### Reach me out

* [**Git**](https://github.com/alexcalaca)[**h**](https://linkedin.com/in/alexandrecalacaofficial)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**b**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**L**](https://linkedin.com/in/alexandrecalacaofficial)[**inked**](https://github.com/alexcalaca)[**In**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashn**](https://linkedin.com/in/alexandrecalacaofficial)[**ode**](https://github.com/alexcalaca)
    
* [**Y**](https://linkedin.com/in/alexandrecalacaofficial)[**o**](https://github.com/alexcalaca)[**u**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**tube**](https://github.com/alexcalaca)
    

---

### Final thoughts

Thank you for reading this article. If you have any questions, thoughts, suggestions, or corrections, please share them with us. We appreciate your feedback and look forward to hearing from you. Feel free to suggest topics for future blog articles. Until next time!

---