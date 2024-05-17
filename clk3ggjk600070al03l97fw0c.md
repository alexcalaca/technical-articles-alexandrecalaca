---
title: "Comprehensive guide to the blank? method in Rails"
datePublished: Sat Jul 15 2023 03:35:36 GMT+0000 (Coordinated Universal Time)
cuid: clk3ggjk600070al03l97fw0c
slug: comprehensive-guide-to-the-blank-method-in-rails
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/4Zaq5xY5M_c/upload/bb9ba8dc148ec04d188fc12cb3539eed.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails

---

> TL;DR: The blank? method returns true if the object is nil, an empty value (string, array or hash), a whitespace-only string or false.

---

## Definition

The `blank?` method is a Rails extension to Ruby's Object class. It is used to determine if an object is considered "blank" or empty.

---

## The ActiveSupport library

### Definition

`ActiveSupport` is a core component of the Ruby on Rails framework. It is a separate gem that provides a collection of utility classes and extensions that enhance the functionality of Ruby and make development in Rails more productive and efficient.

In Rails, the ActiveSupport library builds on top of Ruby's core extensions and provides additional functionality.

---

### Ruby's core extension

Ruby's core extensions in ActiveSupport refer to the additional methods and functionalities that ActiveSupport adds to the core Ruby classes.

These extensions enhance the capabilities of Ruby and make certain operations more convenient and expressive.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689309622068/c49e3b9f-cf1e-47b7-b642-ec9de6093e9a.png align="center")

These extensions can be seen Inside the directory `activesupport/lib/active_support/core_ext` or through [this link](https://github.com/rails/rails/tree/main/activesupport/lib/active_support/core_ext).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689309671982/9cfa0507-7eaa-469e-aae9-b86b41ae1c9b.png align="center")

These classes have additional methods and functionalities making the code more concise, readable, and efficient.

---

### Implementation

The blank? method is not implemented in a single Rails file. Instead, it is implemented through a combination of Ruby core extensions and Rails' ActiveSupport library.

The core extension for `blank?` is defined in the Object class, which is part of Ruby's standard library. The Rails enhancement of the `blank?` method can be found in the `Object` folder: `activesupport/lib/active_support/core_ext/object` or through [this link](https://github.com/rails/rails/tree/main/activesupport/lib/active_support/core_ext/object).

To be more specific, the Rails file responsible for the `blank?` method is in `activesupport/lib/active_support/core_ext/object/blank.rb`.

---

### The Object's class extension

Rails extends core Ruby classes like Object, String, Array, Hash, and others with additional methods through the ActiveSupport library. These extensions provide Rails-specific functionality and convenience methods that are commonly used in Rails development.

When it comes to the Object class, any method included in that, it becomes available to all objects, since Object is the superclass of all other classes in Ruby.

When Rails loads, it extends the Object class with additional methods, including `blank?`, making them accessible to all objects in a Rails application.

Rails allows you to call `blank?` on any object in your Rails application. This is particularly useful when working with form inputs, database values, or user input, where you need to check if a value is empty, nil, or contains only whitespace.

---

---

## The `blank?` method

The `blank?` method is originally from Ruby. In Ruby on Rails, the `blank?` method is a convenient way to check whether a value is:

* empty, including `nil`;
    
* an empty string (`""`);
    
* a whitespace-only string; of
    
* false.
    

Since the

You can use it on various data types such as strings, arrays, hashes, and more.

---

### Usage

In order to use the `blank?` method, we just need to use the following syntax:

```apache
object.blank?
```

When a Rails application loads, it extends the `Object` class by adding extra methods, including `blank?`, which become available to all objects within the Rails environment.

The Rails enhancement of the `blank?` method can be located in the `Object` folder at the following path: `activesupport/lib/active_support/core_ext/object`. You can find the specific implementation of the `blank?` method there.

---

### Parameters

The `blank?` method in Rails does not accept any parameters. It is a predicate method that can be called on an object directly without passing any arguments.

The purpose of the `blank?` method is to determine if an object is empty, false, nil, or consists only of whitespace. It returns `true` if the object is considered blank and `false` otherwise.

---

### Return

The `blank?` method is a predicate method, so, it returns true or false.

```apache
2.7.2 :001 > "".blank?
 => true 
2.7.2 :002 > "something".blank?
 => false 
2.7.2 :003 > [nil].blank?
 => false 
2.7.2 :004 > [key: nil].blank?
 => false
```

A `predicate` method, in the context of programming, is a method that returns a boolean value (true or false) based on a condition or property of an object.

The name "predicate" is derived from logic and mathematics, where a predicate is a statement that can be true or false.

In many programming languages, including Ruby, predicate methods conventionally end with a question mark (`?`) to indicate that they return a boolean value.

These methods are often used to query or check the state of an object.

---

### Rails implementation

The Rails file responsible for the `blank?` method is in `activesupport/lib/active_support/core_ext/object/blank.rb`.

Let's take a look at part of the file

```apache
class Object
  # An object is blank if it's false, empty, or a whitespace string.
  # For example, +nil+, '', '   ', [], {}, and +false+ are all blank.
  #
  # This simplifies
  #
  #   !address || address.empty?
  #
  # to
  #
  #   address.blank?
  #
  # @return [true, false]
  def blank?
    respond_to?(:empty?) ? !!empty? : !self
  end
```

---

### def blank?

Since the method name ends with `?`, it shows that this is a predicate method. In this case, we can expect to get a true or false by using this method.

---

### respond\_to?(:empty?)

This code line uses the ternary if statement to evaluate whether the object responds to `empty?` or not.

In Ruby, many classes implement an `empty?` method to check if the object has no elements or content.

If the object has an `empty?` method, the code proceeds to the expression after the `?`. Otherwise, it executes the expression after the `:`.

---

### ||empty?

`!!empty?` is used to explicitly convert the result of empty? to a boolean value. It ensures that the result is either true or false.

If the object's \`empty?\` method returns true, the expression evaluates to true. If it returns false or the object doesn't have an empty? method, it proceeds to the next step.

The double `!` is to make sure that it always return a boolean value.

---

### !self

`!self` checks if the object itself is "truthy" or "falsy".

In Ruby, `nil` and `false` are considered falsy, while everything else is considered truthy. So, if the object is `nil` or `false`, the expression evaluates to `true`. Otherwise, it evaluates to `false`.

If the object doesn't have an `empty?` method or the `empty?` method returns `false`, it checks if the object itself is `nil` or `false` to determine if it's considered blank. The method ultimately returns `true` if the object is blank, and `false` otherwise.

---

### Summary

Summing up, the `blank?` method first checks if the object has an `empty?` method.

If it does, it uses that method to determine if the object is empty. If the object doesn't have an `empty?` method or the `empty?` method returns `false`, it checks if the object itself is `nil` or `false` to determine if it's considered blank.

The method ultimately returns `true` if the object is blank, and `false` otherwise.

---

## Algorithm efficiency

### Time complexity

The time complexity of calling `empty?` on the object will depend on the implementation of the `empty?` method for that particular object's class.

As an example, since arrays are objects with constant-time length checks, the time complexity is constant time O(1).

To clarify, the time complexity of a length check for arrays is indeed O(1) because the length of an array is typically stored as a property or attribute of the array object. Accessing the length property directly requires a constant amount of time, regardless of the size of the array.

---

### Space complexity

The space complexity of the `blank?` method is constant (O(1)) as it does not depend on the size of the input.

The method does not create any significant additional data structures or use additional memory that scales with the input.

In summary, the time complexity of the `blank?` method can vary from O(1) to O(n), while the space complexity is constant O(1).

---

## **Celebrate**

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---