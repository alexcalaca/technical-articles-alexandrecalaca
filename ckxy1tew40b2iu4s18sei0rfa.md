---
title: "In Ruby, How to get the number of elements in an array?"
datePublished: Sun Jan 02 2022 02:11:59 GMT+0000 (Coordinated Universal Time)
cuid: ckxy1tew40b2iu4s18sei0rfa
slug: in-ruby-how-to-get-the-number-of-elements-in-an-array
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1640840812785/PsHowojLE.png
tags: ruby, programming, ruby-on-rails

---

First of all, I just want to say that you guys rock ;-)
Thanks for all the support.

Anyway, let's get down to business. This article is about how to get the number of elements in an array in Ruby.

### Introduction
One of the craziest things about Ruby is that there are a bunch of ways to do the same thing, it might scare some newcomers.

Let's check two great ways to check the number of elements in an array.

### First way - Using the `length` method
The `length` method is available in many classes in Ruby, such as the Array and String class. It's used to return the number of elements in an array or the number of characters in a string.

```
irb(main):002:0> array = [1, 2]
irb(main):003:0> array.length
=> 2
irb(main):004:0> "string".length
=> 6
```

A `NoMethodError` is displayed if the `length` method is used in an integer or float type.

```
irb(main):001:0> 23.length
Traceback (most recent call last):
        4: from /usr/local/bin/irb:23:in `<main>'
        3: from /usr/local/bin/irb:23:in `load'
        2: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        1: from (irb):1
NoMethodError (undefined method `length' for 23:Integer)
``` 

```
irb(main):005:0> 2.3.length
Traceback (most recent call last):
        5: from /usr/local/bin/irb:23:in `<main>'
        4: from /usr/local/bin/irb:23:in `load'
        3: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        2: from (irb):4
        1: from (irb):5:in `rescue in irb_binding'
NoMethodError (undefined method `length' for 2.3:Float)```

It's possible to have an array with 0 elements. So, it's also possible to return 0.

```
irb(main):001:0> array = []
irb(main):002:0> array.class
=> Array
irb(main):003:0> array.length
=> 0
```

The `size` method is an alias for the `length` method, so, the principles/ideas are all the same. They share the same source code.

Check one example
```
irb(main):004:0> array
=> []
irb(main):005:0> array.size
=> 0
irb(main):006:0> array = [2, 3, "hi"]
irb(main):007:0> array.size
=> 3
```
In both scenarios, the result is the same.
```
irb(main):008:0> array
=> [2, 3, "hi"]
irb(main):009:0> array.size
=> 3
irb(main):010:0> array.length
=> 3
``` 

### Second way - Using the `count` method
It also returns the number of elements, however, it offers new features and possibilities according to the arguments added to it.

First things first, with no arguments, the behavior is the same. Check it out.
```
irb(main):014:0> array
=> [2, 3, "hi", 4]
irb(main):015:0> array.length
=> 4
irb(main):016:0> array.size
=> 4
irb(main):017:0> array.count
=> 4
```

In string types, `length` and the `size` methods have the same result.  Just remember that the `size` method is just an alias for the `length` method.
```
irb(main):001:0> "string".length
=> 6
irb(main):002:0> "string".size
=> 6
```
In the String class, the `count` method needs an argument, so, the result is not as the same as the other methods. In this case, an `ArgumentError` error is displayed.

```
irb(main):003:0> "string".count
Traceback (most recent call last):
        5: from /usr/local/bin/irb:23:in `<main>'
        4: from /usr/local/bin/irb:23:in `load'
        3: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        2: from (irb):3
        1: from (irb):3:in `count'
ArgumentError (wrong number of arguments (given 0, expected 1+))
```
Since the goal of this article is to focus on how to get the number of elements in an array, we're not going to check the details of the use of the `count` method available in the String class. Ok?

Anyway, the `count` method allows the use of conditions. Let's check one example:
```
irb(main):001:0> array = [2, 3, "hi", 3]
irb(main):002:0> array.count(3)
=> 2
```
In the previous example, the `count` method was used to count the occurrences of the number 3. The result was 2.

There are more details to deep dive into the `count` method, but this is going to be another article of the blog.


### Conclusion
**What's the best option?**
In order to choose, keep in mind 2 things:
- Use the `count` method if there are special needs, such as conditions and/or blocks;
- Use  the`length` or the `size` method if the goal is only to get the number of elements in an array;

**Still don't know what to choose?
**Choose the `length` or the `size` method, because their performance is better than the `count` method.

