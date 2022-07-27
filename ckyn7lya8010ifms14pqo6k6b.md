## What are predicate methods? How to identify them in Ruby?

### Goal
The goal of this article is to talk about how predicate methods work. Examples are going to be provided using the programming language `Ruby`.

### Introduction
In order to grasp the idea, let's see the definition of the word `predicate` in some fields of study.

#### Discrete Mathematics
In Discrete Mathematics, a predicate is a statement or declaration or a mathematical assertion that contains variables, and it returns true or false according to the variable's values.

#### Natural language
In natural language grammar, it doesn't really matter the language, the predicate is a statement about a subject, which is either true or false.
In other words, the predicate is the part of a sentence that includes the verb and a complement.

As an example, let's check the following sentence:
`The girls went to the park`. The predicate is `went to the park`. 

#### Programming
In other words, a predicate is a function that accepts arguments and return a boolean value or something like that. Basically, if the function asks any question to the object state or value, expecting the result to be true or false, then, these are called predicate functions or methods.
The idea is to check if the input meets one specific condition.

#### Ruby
In Ruby, there's a naming convention for predicate methods: they end with a question mark.
IF followed, this convention improves the readability of the code, since it looks like a question in English.

Let's check some examples of predicate methods:
- `integer?` It checks if the value is an integer or not.
```
irb(main):001:0> 4.integer?
=> true
``` 

- `odd?` it returns true if the value is odd number
```
irb(main):002:0> 3.odd?
=> true
irb(main):003:0> 4.odd?
=> false
``` 

- `empty?` It returns true if the length of self (current object) is zero, false otherwise.
```
irb(main):004:0> "alexandre-calaca".empty?
=> false
irb(main):005:0> "".empty?
=> true
``` 

### Conclusion
In this article, it was possible to understand what predicate methods are.

Hope it was useful.

That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article.
