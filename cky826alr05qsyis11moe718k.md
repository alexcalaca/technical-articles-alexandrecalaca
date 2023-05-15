---
title: "How to check if an object is present in an array in Ruby?"
datePublished: Sat Jan 04 2020 02:17:09 GMT+0000 (Coordinated Universal Time)
cuid: cky826alr05qsyis11moe718k
slug: how-to-check-if-an-object-is-present-in-an-array-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1640702705220/aVmC-Kclu.png
tags: ruby, programming, ruby-on-rails

---

> TL;DR: `include?` is the best approach

---

### Greetings

Hey, It's Alexandre Calaça here. Hope you're good.

---

### Introduction

Today, let's work on 3 different approaches to check if an object is present in the array in Ruby. Every approach has their cons and pros, however I totally recommend the third approach.

Let's rock? lol

---

### Approaches

Basically, there are three approaches:

* First approach - Using the `index` method
    
* Second approach - Using the `any?` method
    
* Third approach - Using the `include?` method
    

---

### First approach - Using the `index()` method

The `index()` method returns the index of the first object in an array such that the object is, it's based on the number used as a parameter.

Here's the catch, it doesn't return a boolean value. It returns an enumerator.

In the following example, it returns number 4 because it is the index of the specified value, number 9.

```apache
irb(main):001:0> array = [1, 31, 3, 7, 9, 99]
irb(main):011:0> array.index(9)
=> 4
```

`nil` is returned if no results are found

```apache
irb(main):001:0> array = [1, 31, 3, 7, 9, 99]
irb(main):012:0> array.index(87)
=> nil
```

It returns the array itself if no parameter is given.

```apache
irb(main):013:0> array.index()
=> #<Enumerator: [1, 31, 3, 7, 9, 99]:index>
```

If it's really necessary a boolean value return, then, we need to look for a way to workaround this problem.

IF the return value is different than 0, then, the object is in the array.

```apache
irb(main):001:0> array = [1, 31, 3, 7, 9, 99]
irb(main):014:0> array.index(1) != nil
=> true
irb(main):015:0> array.index(2) != nil
=> false
```

---

### Second approach - Using the `any?` method

The `any?` method is very powerful and it deserves a full article about its features. In this article, let's check only on case scenario.

In the following example, the \*\*my\_array \*\*variable has 6 elements. The `any?` method takes a block and it is looking for the number 3, so, the return is true.

```apache
irb(main):001:0> my_array = [1, 31, 3, 7, 9, 99]
irb(main):002:0> my_array.any? {|i| i == 3}
=> true
```

The return is false in the following example, since the number 4 is not in the my\_array variable.

```apache
irb(main):001:0> my_array = [1, 31, 3, 7, 9, 99]
irb(main):002:0> my_array.any? {|i| i == 4}
=> false
```

---

### Third approach - Using the `include?` method

The include? method returns true if the specified value is in the array and false if not. Equality is tested using ==.

The boolean value true is returned when the object is in the array.

```apache
irb(main):001:0> array = [1, 31, 3, 7, 9, 99]
irb(main):007:0> array.include?(3)
=> true
```

The boolean value `false` is returned when the object is NOT in the array.

```apache
irb(main):001:0> array = [1, 31, 3, 7, 9, 99]
irb(main):008:0> array.include?(4)
=> false
```

The method `member?()` is also available, it is an alias for the method `include?()`, so, you can use which one you want.

```apache
irb(main):001:0> array = [1, 31, 3, 7, 9, 99]
irb(main):004:0> array.member?(1)
=> true
irb(main):007:0> array.include?(3)
=> true
irb(main):008:0> array.include?(4)
=> false
irb(main):009:0> array.member?(4)
=> false
```

---

### Conclusion

How to pick the best option? If the goal is to only check if an object is present in an array, then, use the `member?` or the `include?` method.

If you need more features or options, such as the possibility of checking if any of the array items have a specific length, then, use the `any?` method.

If you're interested in the index of the given parameter, then, use the `index` method.

That's all for today. Reach me out if you have any questions, guys.

---