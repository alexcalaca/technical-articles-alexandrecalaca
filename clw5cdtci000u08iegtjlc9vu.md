---
title: "How to calculate the square root of a number in Ruby?"
datePublished: Mon May 13 2024 19:13:31 GMT+0000 (Coordinated Universal Time)
cuid: clw5cdtci000u08iegtjlc9vu
slug: how-to-calculate-the-square-root-of-a-number-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/MskbR8VLNrA/upload/547cd5cd63361f76ef0611c0c8cb8795.jpeg
tags: ruby, programming-tips, alexandrecalaca

---

---

## Introduction

Before we proceed, it's crucial to note that calculating the square root of a number from scratch is indeed possible, although it's not the focus of this post.

Instead, we'll explore how to efficiently calculate the square root using the sqrt method, which is available in both the Math module and the Integer class.

---

## Solutions

To calculate the square root, you have two options:

### **Using Integer class**

```javascript
Integer.sqrt(number)
```

### **Using Math module**

```javascript
Math.sqrt(number)
```

---

### Syntax

**Integer class**

```javascript
Integer.sqrt(number)
```

**Math module**

```javascript
Math.sqrt(number)
```

---

### Parameters

Both `Integer.sqrt()` and `Math.sqrt()` require a non-negative number as a parameter. It's essential to be aware that the Math module treats the parameter as a float type, while the Integer class considers it an integer type.

If the parameter passed to `Integer.sqrt()` is not an integer (e.g., a float or a string), it will be converted to an integer before the square root is calculated. Similarly, for the `Math.sqrt()` method, the parameter is converted to a float first.

---

### Errors

However, when dealing with string parameters, complications arise. If the parameter is a string, a TypeError will be raised.

It's crucial to handle such scenarios to avoid unexpected errors in your code.

A `TypeError` is returned if the parameter value is a String.

```javascript
irb(main):006:0> Integer.sqrt('4')
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):5
        2: from (irb):6:in `rescue in irb_binding'
        1: from (irb):6:in `sqrt'
TypeError (no implicit conversion of String into Integer)
irb(main):007:0> Math.sqrt('4.0')
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):6
        2: from (irb):7:in `rescue in irb_binding'
        1: from (irb):7:in `sqrt'
TypeError (can't convert String into Float)
```

A `Math::DomainError` is returned if a negative value is used as a parameter.

```javascript
irb(main):001:0> Integer.sqrt(-2)
Traceback (most recent call last):
        5: from /usr/local/bin/irb:23:in `<main>'
        4: from /usr/local/bin/irb:23:in `load'
        3: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        2: from (irb):1
        1: from (irb):1:in `sqrt'
Math::DomainError (Numerical argument is out of domain - "isqrt")
irb(main):002:0> Math.sqrt(-2)
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):1
        2: from (irb):2:in `rescue in irb_binding'
        1: from (irb):2:in `sqrt'
Math::DomainError (Numerical argument is out of domain - "sqrt")
```

An `ArgumentError` is returned if the given number of parameters is different than 1, since it is expected 1 parameter.

```javascript
irb(main):010:0> Integer.sqrt
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):9
        2: from (irb):10:in `rescue in irb_binding'
        1: from (irb):10:in `sqrt'
ArgumentError (wrong number of arguments (given 0, expected 1))
irb(main):011:0> Math.sqrt
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):10
        2: from (irb):11:in `rescue in irb_binding'
        1: from (irb):11:in `sqrt'
ArgumentError (wrong number of arguments (given 0, expected 1))
```

---

### **Return Value**

#### **Integer.sqrt()**

The `Integer.sqrt()` method returns the integer square root of the non-negative integer parameter.

For example, the largest non-negative integer square root of 5 is 2. This method specifically returns the largest integer number.

```javascript
irb(main):001:0> Integer.sqrt(1)
=> 1
irb(main):002:0> Integer.sqrt(2)
=> 1
irb(main):003:0> Integer.sqrt(3)
=> 1
irb(main):004:0> Integer.sqrt(4)
=> 2
irb(main):005:0> Integer.sqrt(5)
=> 2
```

The square root of 2 is 1.4142135623730951, but since the `Integer.sqrt()` method specifically deals with integers, it returns the largest integer, which is 1.

#### **Math.sqrt()**

On the other hand, the `Math.sqrt()` method is capable of returning a float value.

```javascript
irb(main):006:0> Math.sqrt(1)
=> 1.0
irb(main):007:0> Math.sqrt(2)
=> 1.4142135623730951
irb(main):008:0> Math.sqrt(3)
=> 1.7320508075688772
irb(main):009:0> Math.sqrt(4)
=> 2.0
```

Here, `Math.sqrt()` provides the accurate square root, including decimal values.

---

### **Conclusion**

In summary, when precision with decimal values is required, the `Math.sqrt()` method is the preferable choice.

If you specifically need the largest integer result, `Integer.sqrt()` is suitable. Feel free to reach out if you have any questions or further inquiries.

---

## Done

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**L**](https://linkedin.com/in/alexandrecalacaofficial)[**inkedI**](https://github.com/alexcalaca)[**n**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Hashn**](https://linkedin.com/in/alexandrecalacaofficial)[**ode**](https://github.com/alexcalaca)
    
* [**Y**](https://www.youtube.com/@alexandrecalacaofficial)[**ou**](https://linkedin.com/in/alexandrecalacaofficial)[**tube**](https://github.com/alexcalaca)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!