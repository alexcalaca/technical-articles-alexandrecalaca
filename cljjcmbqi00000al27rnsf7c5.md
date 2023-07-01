---
title: "How to see all available associations of one specific object in Rails?"
datePublished: Sat Jul 01 2023 01:52:44 GMT+0000 (Coordinated Universal Time)
cuid: cljjcmbqi00000al27rnsf7c5
slug: how-to-see-all-available-associations-of-one-specific-object-in-rails
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688176119303/9446a85a-8a3f-4bfd-91b4-48e9730b5564.png
tags: programming-blogs, ruby, web-development, ruby-on-rails

---

> ***TL***;***DR: The secret is the method*** `reflect_on_alll_associations`

---

## Problem

How to see all available associations of one specific object in Rails?

---

## Introduction

When working on software development, developers often need to find strong relationships between objects in their database.

Ruby on Rails provides a powerful feature called associations, which allows us to establish connections between different models and access related data effortlessly.

Besides using Rails models to check the relationships, there's an interesting approach that is usually unknown by Rails developers.

In this article, we will explore a simple yet effective approach to gain insights into all available associations of a particular object within a Rails application.

---

## Context

Basically, we need to find the object, use the keyword `class` on it and then call the `reflect_on_all_assotions` method.

This solution was tested in the following Rails versions: 3.2, 6.1 and 7.0.

Let's dive in.

---

![três gatinhos de cores sortidas](https://images.unsplash.com/photo-1566847438217-76e82d383f84?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80 align="left")

---

### Situation

Let's think about a User model. The User model has relationships with posts, comments and likes.

---

### Find the object

Open `rails console`.

I'm going to use the last `User`.

```ruby
User.last
```

---

### Get the class

In order to use the methods provided by the `class` keyword, let's get the class of the object:

```ruby
User.last.class
```

Now, we'll be able to use the `reflect_on_all_associations` built-in Ruby function:

```ruby
User.last.class.respond_to?(:reflect_on_all_associations)
```

The previous method returns true, since the `reflect_on_all_associations` method is available to the object caller.

---

### Retrieve associations information

```ruby
User.last.class.reflect_on_all_associations
```

The result is going to be an array of associations.

```ruby
User.last.class.reflect_on_all_associations.is_a?(Array)
```

As you can see, the output is too broad, it's possible to narrow it down a little.

In case you want to learn more about the `reflect_on_all_associations` method and its class, click here (article in progress).

---

### Refine the result

Let's retrieve the associations and store them in a variable:

```ruby
associations = user.class.reflect_on_all_associations
```

Select only `name`, `type` and `class_name`:

```ruby
associations.each do |association|
  puts "Name: #{association.name}"
  puts "Type: #{association.macro}"
  puts "Associated Class: #{association.class_name}"
  puts "---------------------"
end
```

The previous code iterates over the associations' array and prints the name, type (macro), and associated class name for each association.

It's used the name, macro, and class\_name methods of the AssociationReflection objects.

The output would be something like this:

```ruby
Name: posts
Type: has_many
Associated Class: Post
---------------------
Name: comments
Type: has_many
Associated Class: Comment
---------------------
Name: likes
Type: has_many
Associated Class: Like
---------------------
```

---

## **Be happy**

You got here. Way to go!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome. By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---