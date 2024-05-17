---
title: "Learning how to use the magnitude method in Ruby"
datePublished: Wed Mar 24 2021 02:59:55 GMT+0000 (Coordinated Universal Time)
cuid: ckygoe2ws01si35s1969ucoed
slug: learning-how-to-use-the-magnitude-method-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1641952922724/xfrihtw9V.png
tags: ruby, programming, ruby-on-rails

---

What's up, guys? 
I have been great, thanks.
First of all, I want to thank everyone for so many nice messages.

### Intro
Today, I want to share with you how to use the `magnitude` ruby method. I'm not sure if this is the first time that you have ever heard about this method, but it is a good opportunity to learn it.

### What does the `magnitude` method do?
The `magnitude` method belongs to the `numeric` class. In Ruby, the numeric class is the highest-level class for numbers. 

The method returns the absolute value of a given number.

There's an available alias for this method, which is `abs`.

### What's an absolute value?
I'm not a math geek, but this answer is kinda simple. The absolute value of a number x is its non-negative version, so, it's the number without the negative sign.

For example, the absolute value of the number -4 is 4. The absolute value of the positive 4 is also 4. It doesn't matter the parameter, the absolute value is always the positive version.

### Using the `magnitude` method
#### Syntax
The syntax is very simple:
``` 
number.magnitude
``` 
`number` is the value we want to check the absolute version.
`.` is how we call the method.
`abs` is the method.

#### Get down to business
Let's check it out:
```
irb(main):006:0> -8.magnitude
=> 8
```
The absolute value of a positive number is the number itself
```
irb(main):005:0> 8.magnitude
=> 8
```

Since The `magnitude` method also works with the float type, it's possible to use in the following ways:
```
rb(main):007:0> -5.4.magnitude
=> 5.4
irb(main):008:0> 5.4.magnitude
=> 5.4
```

A `NoMethodError` is displayed if it's used with a data type that it doesn't inherit from the `numeric class`.
```
irb(main):009:0> "2".magnitude
Traceback (most recent call last):
        4: from /usr/local/bin/irb:23:in `<main>'
        3: from /usr/local/bin/irb:23:in `load'
        2: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        1: from (irb):9
NoMethodError (undefined method `magnitude' for "2":String)
``` 

#### Summing up:
- Syntax: numericvalue.magnitude()
- Parameter: numeric value which is to be converted to absolute value.
- Return: absolute value of the passed numeric value.

### Conclusion
In this article, it was possible to learn how to use the `magnitude` method. It was also possible to practice how to get the absolute value of numbers in Ruby.

Hope it was useful.

That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article.