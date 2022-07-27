## How to convert a string to lowercase in Ruby?

### Greetings
Hey,  It's Alexandre Calaça here. Hope you're good.

### Introduction
Today, let's learn and practice  how to convert a string to lowercase in Ruby.

### The `downcase` method
In Ruby, the `downcase` method is used to convert a string to lowercase. It returns a copy of self (current object) with all characters downcased.

#### Syntax
```
"string".downcase
```
or 
```
str.case
```
In the previous example, str is the variable name.

#### Parameters
The `downcase` method doesn't require parameters.

#### Return value
It returns a new lowercase string of the caller. If no conversation is necessary, It returns the original string.

It's possible to return and modify self (current caller) if we use the `bang` operator after the method.

#### Coding time
Let's check the examples and learn from them.

In the following examples,
it's noticeable that:
- The `downcase` method doesn't modify the original string;
- It returns a new lowercase string of the caller;

```
irb(main):001:0> my_string = "ALEXANDRE"
irb(main):002:0> my_string.downcase
=> "alexandre"
irb(main):003:0> my_string
=> "ALEXANDRE"
```
it's possible to see that:
- The `downcase` method returns the same string if no conversion is necessary.
```
irb(main):006:0> my_new_string = "alexandre calaca"
irb(main):007:0> my_new_string.downcase
=> "alexandre calaca"
irb(main):008:0> 
``` 
And that:
- The `bang` operator allows the `downcase` method to modify self.
```
irb(main):012:0> my_string = "AlExAnDrE"
irb(main):013:0> my_string
=> "AlExAnDrE"
irb(main):014:0> my_string.downcase!
=> "alexandre"
irb(main):015:0> my_string
=> "alexandre"
```

### Conclusion
In this article, it was possible to  learn and practice  how to convert a string to lowercase in Ruby. There were excellent examples.

That's all for today.
Reach me out if you have any questions, guys.

```