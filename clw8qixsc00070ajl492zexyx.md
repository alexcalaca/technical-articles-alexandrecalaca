---
title: "Exploring the Power of Ruby's Ensure Keyword"
datePublished: Thu May 16 2024 04:12:43 GMT+0000 (Coordinated Universal Time)
cuid: clw8qixsc00070ajl492zexyx
slug: exploring-the-power-of-rubys-ensure-keyword
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/itriu-lCKzs/upload/1f7d7e4a3f76b7acfd6f44cc04fdc44c.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## Ensure

In Ruby, the `ensure` keyword is used in exception handling to ensure that a certain block of code is always executed regardless of whether an exception is raised or not.

Besides, it provides a mechanism for cleanup or finalization tasks, guaranteeing that essential actions such as releasing resources or providing feedback are carried out consistently.

---

## Exception handling

### The structure

```ruby
begin
  # Code that might raise an exception
rescue SomeError => e
  # Code to handle the exception
else
  # Code that is executed when there's no exception
ensure
  # Code that is always executed, whether an exception is raised or not
end
```

#### begin

This keyword marks the beginning of a block of code where exceptions might occur. Inside this block, you place the code that could potentially raise an exception.

#### rescue SomeError =&gt; e

In this line, rescue is used to catch any exceptions that occur within the begin block.

SomeError is the class of the exception that you want to catch. You can replace SomeError with the specific type of exception you expect to handle, or you can use `StandardError` to catch any standard exceptions. The `=> e` part assigns the exception object to the variable `e`, allowing you to access information about the exception.

#### else

This keyword introduces a block of code that is executed when there is no exception raised within the begin block. If no exception occurs, the code within the else block will be executed. This block is optional and is skipped if an exception occurs.

#### ensure

This keyword introduces a block of code that is always executed, regardless of whether an exception was raised or not. It ensures that certain cleanup or finalization tasks are performed, such as closing files, releasing resources, or any other actions that should happen regardless of the program's flow.

---

### Basic execution with no exception

Take a look at the following initial structure

```ruby
begin
  puts "begin"
rescue StandandError => e
  puts "rescue"
else
  puts "else"
ensure
  puts "ensure"
end
```

The following code returns

```ruby
begin
else
ensure
```

The `begin` keyword marks the beginning of the block where code execution starts.  
Since there is no error raised in the begin block, the `rescue` block is skipped.

Since no exception was raised, the `else` block is executed. It prints "`else`" to the console. The `ensure` block is always executed regardless of whether an exception was raised or not. It prints "`ensure`" to the console.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715742570807/22ec629f-7b46-48e2-80b7-ac4e48ade515.png align="center")

---

### Basic execution with an exception raised

Take a look at the following initial structure

```ruby
begin
  puts "begin"
  raise
rescue
  puts "rescue"
else
  puts "else"
ensure
  puts "ensure"
end
```

The following code returns

```ruby
begin
rescue
ensure
```

The `begin` keyword marks the beginning of the block where code execution starts.  
Since there is an error raised in the begin block, the `rescue` block is called.

Since an exception was raised, the `else` block is skipped. The `ensure` block is always executed regardless of whether an exception was raised or not. It prints "`ensure`" to the console.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715743026837/5a00efee-8c53-4f0a-b609-901f21dc015c.png align="center")

---

## Cleanup task

### Definition

> The `ensure` keyword can also be used as a cleanup or finalization task.

It can be seen as a cleanup task because it performs an action that needs to be done regardless of whether an exception occurred or not.

It can also be considered a finalization task because it ensures that certain actions are always performed before the method exits, regardless of whether an exception was raised or not.

---

### Example

In this example, the finalization task is printing "Operation completed.", which indicates the completion of the method's execution.

```ruby
def perform_operation(dividend, divisor)
  result = dividend / divisor  
  ensure
  puts 'Operation completed'
end

puts perform_operation(10, 2)
puts perform_operation(10, 0)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715832422906/6ac9ca9d-5e83-4fc8-8120-0de33ad7cabb.png align="center")

In this case, it's providing feedback or logging information that indicates the completion of an operation.

---

## **Conclusion**

In conclusion, the `ensure` keyword in Ruby serves a crucial role in exception handling, ensuring that certain code blocks are always executed, regardless of whether an exception is raised or not.

It provides a mechanism for cleanup or finalization tasks, guaranteeing that essential actions such as releasing resources or providing feedback are carried out consistently.

Whether managing basic execution flow or handling exceptions, the ensure block adds robustness to Ruby programs by enforcing necessary actions, ultimately contributing to more reliable and maintainable code.

Its versatility makes it a fundamental feature in handling exceptions and ensuring code integrity in Ruby applications.

---

## **Done**

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**H**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ashnode**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thou[**g**](https://github.com/alexcalaca)hts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---