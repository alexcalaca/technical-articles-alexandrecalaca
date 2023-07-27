---
title: "Creating Bulletproof Validations in Ruby on Rails with Custom Validators [Part I ]"
datePublished: Thu May 11 2023 14:44:35 GMT+0000 (Coordinated Universal Time)
cuid: clhj8qhp3000009jk9unh2kjd
slug: creating-bulletproof-validations-in-ruby-on-rails-with-custom-validators-part-i
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/W2pFr3MSYkA/upload/98436497cf39a19b7a16b82657c9df09.jpeg
tags: programming-blogs, ruby, ruby-on-rails, hashnode, 2articles1week

---

---

## Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. I'm so excited that you landed here. Hope you enjoy this new article.

By the way, I would be glad to receive your feedback about it.

Since you're already here, consider follow me on [github](https://github.com/alexcalaca) and here on [Hashnode](https://blog.alexandrecalaca.com/).

You might be interested in checking my complete [articles list in here](https://blog.alexandrecalaca.com/all-articles).

---

## Objective

In this article, we will explore a introduction to validations in Ruby on Rails, with a focus on custom validations in separate classes with Ruby on Rails.

We will cover the basic concepts of validations, specially in Ruby on Rails. We'll see custom methods, custom validators and Rails' approach to validations.

By the end of this article, you will have a basic understanding of how validations  work in Rails and how they can benefit your application development process.

Planning of this series:
Part I -  Basic introduction (This article) <br/>
[Part II - Strong foundations](https://blog.alexandrecalaca.com/creating-bulletproof-validations-in-ruby-on-rails-with-custom-validators-part-ii) <br/>
Part III - Implementation

---

## Introduction

When building a Ruby on Rails application, validating input data is crucial to ensuring data integrity and preventing errors. While Rails provides several built-in validation methods, these can quickly become complex and difficult to manage when dealing with complex models or complex validation rules.

To address this problem, it is possible to create custom validation methods as separate classes that can be reused across multiple models.

This approach has several advantages, including making it easier to manage complex validation rules, promoting code reuse, and keeping your models lean and easy to maintain.

---

## Validations

In programming, validation is the process of checking whether the input data or user input satisfies a set of predefined rules or constraints. The purpose of validation is to ensure that the input data is correct and appropriate for its intended use, and to prevent errors or unintended consequences that can occur when invalid or unexpected data is processed.

In web development, for example, validation is often used to ensure that user input in web forms is correct and meets certain requirements, such as being in the correct format, within a certain range, or not containing invalid characters. In other types of applications, validation may be used to check the format or type of data that is being input, or to validate that data conforms to certain business rules or requirements.

Validation can be performed at various points in the application, such as at the user interface level, on the client side using JavaScript, or on the server side using backend programming languages like our beloved Ruby on Rails. The validation process typically involves checking the input data against a set of predefined rules or constraints, and providing feedback to the user if the data is invalid, so they can correct it and resubmit.

---

![brown tabby cat on wooden beam](https://images.unsplash.com/photo-1559624989-7b9303bd9792?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1000&q=80 align="left")

---

## Validations in Ruby on Rails
In Ruby on Rails, validations are used to ensure that the data entered by users is valid and meets certain criteria before it is saved to the database. This helps to maintain data integrity and prevent errors in your application. 

There are basically 3 approaches to validations:
- built-in validation methods
- Custom methods
- Custom validators

---

### built-in validation methods

Rails' current approach to validations is to define them directly in the model classes using Rails' built-in validation methods, such as validates\_presence\_of, validates\_length\_of, validates\_format\_of, etc. This approach works well for simple validations, but can become difficult to manage and maintain as the application grows and the number and complexity of validations increase.

To address this issue, Rails also provides the ability to define custom validations in separate classes and modules, which can be reusable and more modular than defining them directly in the model classes. This approach can be particularly useful for complex or domain-specific validations that are not easily expressed using the built-in validation methods.

---

### Custom methods
It's possible to create custom methods that verify the state of your models and add errors to the errors collection when they are invalid.

These methods can be used to implement validation rules that are not covered by the built-in validation methods or to encapsulate complex validation logic into a separate method.

To use a custom validation method in your model, you need to register it by using the validate class method, passing in the symbol for the validation method's name as an argument.

---

### Custom validators
As it already mentioned, Rails' current approach to validations is to define them directly in the model classes using Rails' built-in validation methods.

When the built-in validation helpers are not enough for our needs, you can write your own validators or validation methods as you prefer.

This article is mainly focused on the power of Custom validators in Ruby on Rails, which are reusable classes that define custom validation rules for your models. They allow you to encapsulate complex validation logic into a separate class, making your code easier to understand and maintain.

To create a custom validator in Rails, you need to define a class that inherits from ActiveModel::Validator and implements a validate method. The validate method should take a single argument, which is the model instance being validated, and add error messages to the model's errors collection if the validation fails.

---

## Steps to implement Custom validators
Check Part III.

---

## Conclusion

In conclusion, using custom validations in separate classes with Ruby on Rails can be a powerful tool for simplifying complex validation rules and promoting code reuse.

By following the steps outlined in this article, you have a basic understanding of how validators work in Ruby on Rails.

Whether you are a seasoned Rails developer or just starting out, custom validators can help you build more robust and maintainable applications.

The next article [Part II](https://blog.alexandrecalaca.com/creating-bulletproof-validations-in-ruby-on-rails-with-custom-validators-part-ii) II is going to extend this article and provide strong foundations to move on with the topic.

Part III is going to cover the implementation of custom validators.

---

## Celebrate

I'm glad you finished it, kudos! you did a great job. You can definitely celebrate!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

## Final thoughts

That's all for today. Thanks for reading this article.

I hope it helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---
