---
title: "Using a ruby method to return the absolute value of a number"
datePublished: Fri Feb 07 2020 16:13:25 GMT+0000 (Coordinated Universal Time)
cuid: ckyabhki803zdnzs15pujhzux
slug: using-a-ruby-method-to-return-the-absolute-value-of-a-number
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1641917598303/LHBkUzoQM.png
tags: ruby, programming, ruby-on-rails, mathematics

---

`Revisited on May 18th, 2023`

---

> TL; DR: The fabulous method is called `abs`

## Greetings

Hey guys.

---

### Intro

In the world of mathematics and programming, absolute numbers play a crucial role in numerous applications. They provide us with a clear and definitive measure, stripping away any notion of direction and leaving us with a value's magnitude alone.

In the realm of Ruby programming, the `abs` method becomes our trusted ally when we seek to harness the power of absolute numbers.

Let's dive in.

---

## Absolute value

### Mathematics

An absolute value, also known as the magnitude, is a mathematical concept that represents the distance of a number from zero on a number line. It disregards the number's direction or sign and focuses solely on its numerical value. In other words, the absolute value of a number is always positive or zero.

For example, consider the number line with points representing -5, -3, 0, 2, and 4. The absolute value of -5 is 5, the absolute value of -3 is 3, the absolute value of 0 remains 0, the absolute value of 2 is 2, and the absolute value of 4 is 4. Regardless of the numbers' position on the number line, their absolute values provide a measure of their magnitude without considering their positive or negative nature.

---

### Programming

In programming, the absolute value is an essential concept for performing calculations, comparisons, and transformations. Many programming languages, including Ruby, provide built-in functions or methods, such as the `abs` method in Ruby, to conveniently obtain the absolute value of a number without the need for manual calculations.

---

## The Abs method

The `abs` method in Ruby is a versatile tool that allows us to effortlessly obtain the absolute value of a number. Whether we're dealing with integers, floats, or complex numbers, the `abs` method comes to our rescue, providing a concise and elegant solution to ensure our calculations remain accurate and reliable.

Throughout our journey, we will witness the `abs` method's ability to transform negative numbers into positive ones, helping us compare values, calculate distances, or enforce constraints in our programs.

---

### Definition

The `abs` belongs to the `numeric` class. In Ruby, the numeric class is the highest-level class for numbers.

The `abs` method returns the absolute value of a given number.

The `magnitude` method is an alias for the `abs` method.

---

### Syntax

The syntax is very simple:

```apache
number.abs
```

`number` is the value we want to check the absolute version. `.` is how we call the method. `abs` is the method.

---

### Coding time

Let's check it out:

```apache
irb(main):006:0> -9.abs
=> 9
```

The absolute value of a positive number is the number itself

```apache
irb(main):005:0> 9.abs
=> 9
```

Since The `abs` method also works with the float type:

```apache
rb(main):007:0> -3.4.abs
=> 3.4
irb(main):008:0> 3.4.abs
=> 3.4
```

A `NoMethodError` is displayed if it's used with a data type that it doesn't inherit from the `numeric class`.

```apache
irb(main):009:0> "1".abs
Traceback (most recent call last):
        4: from /usr/local/bin/irb:23:in `<main>'
        3: from /usr/local/bin/irb:23:in `load'
        2: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        1: from (irb):9
NoMethodError (undefined method `abs' for "1":String)
```

---

## Summing up:

* Syntax: numericvalue.abs()
    
* Parameter: numeric value which is to be converted to absolute value.
    
* Return: absolute value of the passed numeric value.
    

---

## Final thoughts

In this article, it was possible to learn and practice how to get the absolute value of numbers in Ruby.

Hope it was useful. That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article.
