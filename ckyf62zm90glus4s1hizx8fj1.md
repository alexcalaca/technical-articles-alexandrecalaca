---
title: "In Ruby:
is_a?, kind_of? and instance_of? 
What's the difference?"
datePublished: Tue Mar 09 2021 01:35:18 GMT+0000 (Coordinated Universal Time)
cuid: ckyf62zm90glus4s1hizx8fj1
slug: in-ruby-isa-kindof-and-instanceof-whats-the-difference
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642210239509/oLaJRaMrN.png
tags: ruby, programming, ruby-on-rails

---

How's it going, guys?

### Intro
Today, l'd like to share with you how to understand these three amazing methods. They look similar and we're going to dive into them, in order to check the difference among them.

### Goal
The goal of this article is to understand the differences among them and allow you to pick the best option for your needs.

### Introduction
In Ruby, there are often a bunch of different ways to ways to achieve the same or similar results. Sometimes, it's just a matter of preference or readability of your code.

This is not common in other programming languages, that's why some newcomers might feel uncomfortable.

### The methods
Anyway, about talk these three methods.
They all come from the same class: `Object` and all of them have similar goals, which is to check the type of the current object.

They all return a boolean value (true or false).

We're going to check the difference later. Just bear with me.

#### The `is_a?` method
*Syntax: parameter.is_a?(Class)*
Parameter: The value that it is going to be checked
Method: is_a?
Class: The class that it is going to be compared with
Return: It returns a boolean value (true or false)

The goal of the `is_a?` method is to check if self (The current object) belongs to the compared class or to their ancestors.

Let's check some examples with an integer value:
```
irb(main):002:0> 20.is_a? Integer
=> true
irb(main):003:0> 20.is_a? Numeric
=> true
irb(main):004:0> 20.is_a? Object
=> true
```

Now, more examples, but with a string value this time:
```
irb(main):005:0> "alexandre calaca".is_a? String
=> true
irb(main):006:0> "alexandre calaca".is_a? Object
=> true
```

#### The `instance_of?` method
*Syntax: parameter.instance_of?(Class)*
Parameter: The value that it is going to be checked
Method: instance_of?
Class: The class that it is going be compared with
Return: It returns a boolean value (true or false)

The goal of the `instance_of?` method is to check if self (The current object) is an instance of the given class. The `instance_of?` method doesn't return true if compared with the class ancestors.

Let's check some examples with a float value:
``` 
irb(main):007:0> (2.4).class
=> Float
irb(main):008:0> (2.4).instance_of? Float
=> true
irb(main):009:0> (2.4).instance_of? Numeric
=> false
irb(main):010:0> (2.4).instance_of? Object
=> false
``` 
Now, let's use an array for testing.
```
irb(main):014:0> [1, 0, 2, 4].class
=> Array
irb(main):015:0> [1, 0, 2, 4].instance_of? Array
=> true
irb(main):016:0> [1, 0, 2, 4].instance_of? Object
=> false
```


#### The `kind_of?` method
*Syntax: parameter.kind_of?(Class)*
Parameter: The value that it is going to be checked
Method: kind_of?
Class: The class that it is going to be compared with
Return: It returns a boolean value (true or false)

The `kind_of?` and `is_a?` methods are the same. 

Let's check the examples anyway:
```
irb(main):014:0> [1, 0, 2, 4].class
=> Array
irb(main):015:0> [1, 0, 2, 4].instance_of? Array
=> true
irb(main):016:0> [1, 0, 2, 4].instance_of? Object
=> false
irb(main):017:0> [21, 40, 12, 34].is_a? Array
=> true
irb(main):018:0> [21, 40, 12, 34].kind_of? Array
=> true
irb(main):019:0> [21, 40, 12, 34].is_a? Object
=> true
irb(main):020:0> [21, 40, 12, 34].kind_of? Object
=> true
irb(main):021:0> [21, 40, 12, 34].is_a? Integer
=> false
irb(main):022:0> [21, 40, 12, 34].kind_of? Integer
=> false
```

### Summing up:
All the 3 methods:
- Belong to the `Object` class;
- Require a parameter, which is the value that it is going to be compared with;
- Return a boolean value (true or false);
- Return `true` if the current object is an instance of the given class;

How about the ancestors of the given class?
Here is the difference, the `instance_of?` method only returns true if self is an instance of the given class, otherwise false.

The `is_a?` and the `kind_of?` methods return true if self is an instance of the given class  or if the class argument is an ancestor of the singleton class of self (the current object).

Let's check these examples with an integer data type.
```
irb(main):023:0> 10.is_a? Numeric
=> true
irb(main):024:0> 10.instance_of? Numeric
=> false
``` 


### Conclusion
In this article, it was possible to understand how the three methods work: `is_a?`, `kind_of?` and `instance_of?`.
Besides, we were able  to recognize the similarities and the difference among these three Ruby methods.

Hope it was useful.

That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article. 


