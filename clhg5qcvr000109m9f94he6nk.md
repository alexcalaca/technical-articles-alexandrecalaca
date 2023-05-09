---
title: "Ruby: Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part II]"
datePublished: Tue May 09 2023 10:57:12 GMT+0000 (Coordinated Universal Time)
cuid: clhg5qcvr000109m9f94he6nk
slug: ruby-maximizing-the-usage-of-the-enumerable-module-for-better-code-efficiency-part-ii
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/UJN_XAg0ECI/upload/97069c69f3d0c218fb6199959760c777.jpeg
tags: ruby, web-development, ruby-on-rails, hashnode, 2articles1week

---

---

### Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. I'm so excited that you landed here. Hope you enjoy this new article.

By the way, I would be glad to receive your feedback about this one and other articles.

---

### Objective

This article [`Ruby: Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part I]`](https://blog.alexandrecalaca.com/ruby-maximizing-the-usage-of-the-enumerable-module-for-better-code-efficiency-part-i) provided an introduction to the Enumerable module.

Part II is going to cover its usage, core methods, module's inclusion and enumerable objects.

Stay tuned!

---

### Enumerable Module

This module provides a set of methods that can be used to iterate over the elements of a collection and perform various operations on them. This collection needs to be an enumerable object.

Let's dive it deeper.

---

### Collections

In case you want to review this topic, check the following article: [`Ruby: Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part I.`](https://blog.alexandrecalaca.com/ruby-maximizing-the-usage-of-the-enumerable-module-for-better-code-efficiency-part-i)

---

### Creation in Ruby

In case you want to review this topic, check the following article: [`Ruby: Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part I.`](https://blog.alexandrecalaca.com/ruby-maximizing-the-usage-of-the-enumerable-module-for-better-code-efficiency-part-i)

---

### Module

In case you want to review this topic, check the following article: [`Ruby: Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part I.`](https://blog.alexandrecalaca.com/ruby-maximizing-the-usage-of-the-enumerable-module-for-better-code-efficiency-part-i)

---

### Instantiation

Modules cannot be instantiated and Enumerable as well, since Enumerable is a Module.

You'll get an error if you try to instantiate an Enumerable module.

In Rails console, take a look

```apache
[47] pry(main)> Enumerable.new
NoMethodError: undefined method `new' for Enumerable:Module
```

It is not possible to instantiate an Enumerable module directly, since Enumerable is a module and not a class. However, you can include the Enumerable module in your own classes to gain access to the methods it defines.

Let's check it.

---

![cat on dining](https://images.unsplash.com/photo-1517330156738-0b67722f3751?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1000&q=80 align="left")

---

### Module's inclusion

```ruby
class MyAmazingCollection
  include Enumerable
  
  def initialize(collection)
    @collection = collection
  end
  
  def each(&block)
    @collection.each(&block)
  end
end
```

Here, we include the Enumerable module in our `MyAmazingCollection` class using the include keyword, and define an each method that simply delegates to the each method of our internal collection.

Now, we can use any of the Enumerable methods on our MyAmazingCollection objects. For example:

```ruby
my_collection = MyAmazingCollection.new([1, 2, 3, 4])
my_collection.each { |n| puts n } # Output: 1 2 3 4
my_collection.map { |n| n * 2 } # Output: [2, 4, 6, 8]
my_collection.select { |n| n.even? } # Output: [2, 4]
```

The previous methods: each, map and select are all available due to the Enumerable Module.

---

### Enumerable Objects

In Ruby, an enumerable object is an object that includes the Enumerable module.

An enumerable object can be any object that represents a collection of items, such as an array, a hash, or a range. When an object includes the Enumerable module, it gains access to several methods that can be used to iterate over the collection and perform operations on its elements.

There are a bunch of different ways to find out if an object is an enumerable object, but let's check one way: Let's consider the following objects:

```ruby
arr = ["alexandre", 2, 5.0]
str = "AC Alexandre Calaca rocks"
```

They represent the following classes:

```ruby
irb(main):048:0> arr.class
=> Array
irb(main):049:0> str.class
=> String
```

Let's check if they are enumerable objects.

```ruby
irb(main):050:0> arr.is_a?(Enumerable)
=> true
irb(main):051:0> str.is_a?(Enumerable)
=> false
```

The `is_a?` method is used to determine if an object is an instance of a specific class or any of its subclasses, including those that have included the Enumerable module. When we call is\_a? on an object that includes Enumerable, we are checking if the object is an instance of a class that includes the Enumerable module.

At the end of the day, It returns true if the object is an instance of the specified class or its subclass, and false otherwise.

---

### Core methods

In Ruby, a `core method` or a `built-in method` is a method that is part of the Ruby language itself, and is available for use without requiring any additional libraries or gems to be installed. Built-in methods are included in the standard library of Ruby, and provide a wide range of functionality for working with data, manipulating objects, and performing a variety of other tasks.

They are considered to be part of the core Ruby language. They are implemented in the Ruby interpreter itself, and can be called on any object that is of the appropriate class.

A famous example of a built-in method in Ruby is the method `puts`.

There are many built-in methods provided by the Enumerable module in Ruby. Some of the most commonly used methods are:

* each: This method iterates over each element in the collection and yields it to the block.
    
* map: This method transforms each element in the collection by applying the block to it and returns a new array with the transformed elements.
    
* select: This method returns a new array containing all elements of the original collection for which the block returns true. In case you're interested, you can check a specific article about the [select](https://blog.alexandrecalaca.com/mastering-the-select-method-in-rails-a-comprehensive-guide-part-i) method. [Check it out here.](https://blog.alexandrecalaca.com/mastering-the-select-method-in-rails-a-comprehensive-guide-part-i)
    
* reject: This method returns a new array containing all elements of the original collection for which the block returns false.
    
* find: This method returns the first element in the collection for which the block returns true, or nil if no such element is found.
    
* any?: This method returns true if the block returns true for at least one element in the collection, otherwise false.
    
* all?: This method returns true if the block returns true for all elements in the collection, otherwise false. none?
    

These methods (and others) can be used with any object that includes the `Enumerable` module.

---

### Usage

The `Enumerable` module is widely used among several Ruby gems and projects. There's a interesting way of checking if a specific class include/use the Enumerable module by using the `ìncluded_modules` methods. Let's check some popular Ruby data types.

```ruby
irb(main):061:0> String.included_modules
=> [Comparable, Kernel]
```

A String class does not include the Enumerable module. Let's see more examples.

```ruby
irb(main):067:0> Array.included_modules
=> [Enumerable, Kernel]
```

```ruby
irb(main):067:0> Array.included_modules
=> [Enumerable, Kernel]
irb(main):068:0> Range.included_modules
=> [Enumerable, Kernel]
irb(main):069:0> Hash.included_modules
=> [Enumerable, Kernel]
irb(main):070:0>
```

The `included_modules` method returns an array of modules included in the given class, so you can use this method to check which other classes include a particular module as well.

---

### Summary

In this article, we learned how to use the `Enumerable module`in Ruby.

This article `Ruby: Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part II]` showed the Enumerable module's usage, core methods, module's inclusion and objects.

---

### Celebrate

If you read the article, right on! you did a great job. You can celebrate for sure!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

### Conclusion

That's all for today. Thanks for reading the article `Maximizing the Usage of the Enumerable Module for Better Code Efficiency [Part II]`

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---