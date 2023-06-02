---
title: "Ruby challenge: Reversing Strings by Words"
datePublished: Fri Jun 02 2023 17:11:50 GMT+0000 (Coordinated Universal Time)
cuid: clietolfm000209jr2g4b8pcf
slug: ruby-challenge-reversing-strings-by-words
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685725351596/2a8cea6f-a76a-46c7-b09b-ae7139e636e6.png
tags: programming-blogs, ruby, development, 2articles1week, crazyblogger

---

---

## Problem

How to revert a String by words. The letters (or words) of your string are in the wrong order.

---

## Situation

Given a String, return a new one in a reversed order by words. As an example, This original string "order correct a not is this " would become "this is not a correct order".

---

## Review

### Strings in programming

A string is a data type commonly used in programming languages to represent a sequence of characters. It is used to store and manipulate textual data. In most programming languages, strings are surrounded by quotation marks, such as single quotes ('') or double quotes ("").

Strings can contain letters, numbers, symbols, and special characters. They can represent words, sentences, paragraphs, file paths, URLs, and more.

---

### Strings in Ruby

In Ruby, a string is an object that represents a sequence of characters. It is an instance of the `String` class, which is part of Ruby's core library. The `String` class provides a wide range of methods and functionalities for manipulating and working with strings.

In terms of inheritance, the `String` class is a subclass of the `Object` class. The `Object` class is the top-level class in Ruby's object hierarchy, and all classes, including `String`, ultimately inherit from it.

---

## Solution

Let's consider the following string

```apache
string = "city the in favorite my is building this"
```

output

```apache
irb(main):001:0> string = "city the in favorite my is building this"
=> "city the in favorite my is building this"
irb(main):002:0> 
```

The proposed solution is

```apache
string.split.reverse.join(' ')
```

output

```apache
irb(main):005:0> string.split.reverse.join(' ')
=> "this building is my favorite in the city"
```

---

## Steps

### Separate the words

```apache
string.split
```

output

```apache
irb(main):007:0> string.split
=> ["city", "the", "in", "favorite", "my", "is", "building", "this"]
```

The `split` method in Ruby is used to divide a string into an array of substrings based on a specified delimiter.

The method takes an optional argument, the delimiter, which determines where the string should be split. If no delimiter is provided, the default delimiter is a whitespace character.

The `split` method scans the original string and identifies occurrences of the delimiter. Each time the delimiter is found, the string is divided into two parts, and the part before the delimiter is added as an element to the resulting array.

As a result, we have an array of words.

---

### Reverse the words

```apache
string.split.reverse
```

output

```apache
irb(main):009:0> string.split.reverse
=> ["this", "building", "is", "my", "favorite", "in", "the", "city"]
```

The `reverse` method in Ruby is used to reverse the order of:

* elements in an array; or
    
* characters in a string.
    

It's important to note that the `reverse` method does not modify the original array or string. Instead, it returns a new object with the reversed order.

---

### Converto into a string

```apache
string.split.reverse.join(' ')
```

output

```apache
irb(main):010:0> string.split.reverse.join(' ')
=> "this building is my favorite in the city"
```

The `join` method in Ruby is used to concatenate the elements of:

* an array, or
    
* collection
    

into a single string.

It takes a separator as an optional argument and returns a new string formed by joining the elements together with the specified separator.

The method iterates through the elements of the array or collection and converts each element to a string.

It then concatenates the elements together, placing the separator between them, and returns the resulting string.

---

#### Without arguments

If called without any arguments, the `join` method concatenates the elements of the array or collection together without any separator. It converts each element to a string and places them side by side.

In our example, the result of

```apache
string.split.reverse.join
```

would be

```apache
irb(main):011:0> string.split.reverse.join
=> "thisbuildingismyfavoriteinthecity"
```

---

#### With arguments

If called with an argument, the argument specifies the separator that should be inserted between the elements when joining them into a single string.

The separator can be any string or character.

The result of

```apache
 string.split.reverse.join('#')
```

would be

```apache
irb(main):012:0> string.split.reverse.join('#')
=> "this#building#is#my#favorite#in#the#city"
```

---

## Celebrate

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

## Let's become friends

* [Github](https://github.com/alexcalaca)
    
* [LinkedIn](https://linkedin.com/in/alexandrecalacaofficial)
    
* [Hashnode](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [Youtube](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## Final thoughts

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.