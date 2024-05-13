---
title: "How to convert a string to lowercase in Ruby?"
datePublished: Mon May 13 2024 19:14:33 GMT+0000 (Coordinated Universal Time)
cuid: clw5cf5cc000b0alc7d0g47lb
slug: how-to-convert-a-string-to-lowercase-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/CffpuUDQ1iU/upload/2f2fb9d763446abc54614bd2dc83ad7f.jpeg
tags: ruby, alexandrecalaca

---

---

## Greetings

Welcome to this simple tutorial!

I'm Alexandre Calaça, and I hope you're doing well.

---

## Introduction

Today, we'll delve into the process of converting a string to lowercase in Ruby. This simple, but fundamental skill that will prove valuable in your Ruby programming journey.

---

## The `downcase` method

In the Ruby programming language, the `downcase` method stands as the go-to solution for transforming a string to lowercase.

This method seamlessly produces a copy of the current object with all its characters converted to lowercase.

> The `downcase` method returns a copy of self (current object) with all characters downcased.

---

### Syntax

```javascript
"string".downcase
str.value
```

In the previous example, `str` is a variable name.

---

### Parameters

The `downcase` method operates without requiring any parameters.

---

### Return Value

When invoked, the method yields a new lowercase string based on the caller. If no conversion is needed, the original string remains unaffected.

Interestingly, appending the bang operator (!) to the method allows for the direct modification of the caller.

---

### Coding Time

Now, let's delve into practical examples to solidify our understanding.

Upon examining the following examples, observe the following key points:

* The `downcase` method preserves the original string, leaving it unaltered.
    
* It generates a fresh lowercase string derived from the original caller.
    

```javascript
irb(main):001:0> my_string = "ALEXANDRE"
irb(main):002:0> my_string.downcase
=> "alexandre"
irb(main):003:0> my_string
=> "ALEXANDRE"
```

it's possible to see that:

* The `downcase` method returns the same string if no conversion is necessary.
    

```javascript
irb(main):006:0> my_new_string = "alexandre calaca"
irb(main):007:0> my_new_string.downcase
=> "alexandre calaca"
irb(main):008:0>
```

And that:

* The `bang` operator allows the `downcase` method to modify self.
    

```javascript
irb(main):012:0> my_string = "AlExAnDrE"
irb(main):013:0> my_string
=> "AlExAnDrE"
irb(main):014:0> my_string.downcase!
=> "alexandre"
irb(main):015:0> my_string
=> "alexandre"
```

---

## **Done**

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me ou**[**t**](https://github.com/alexcalaca)

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**H**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ashnode**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!