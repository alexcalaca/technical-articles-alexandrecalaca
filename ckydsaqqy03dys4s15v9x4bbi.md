## 4  ways to determine whether a value is a number or not in Ruby

How's it going, guys?

### Intro
Today, I want to share with you  4 ways to determine whether a variable is a number or not in Ruby.
The goal is to check if a specific value is a number or not.

### Introduction to the solutions
In Ruby, there are often  synonymous methods so you can use the one that sounds better. It's a matter of preference. This is not common in other programming languages, that's why some newcomers might feel uncomfortable.

This is just an introduction, it doesn't really mean that all the following methods are synonymous, but it's way of understanding how Ruby is flexible when it comes to the solutions of problems.

It's also possible to have many different ways to achieve the same or similar results, so, in this case, it's also a matter of preference and readability of the code.

### 4 approaches
Basically, there are 4 approaches (methods):
- is_a?; 
- class;
- === operator;
- kind_of?;

#### The first approach - The `is_a?` method
*Syntax: parameter.is_a?(Class)*
Parameter: The value that it is going to be checked
Method: is_a?
Class: In this case, the `Integer` class
Return: It returns true or false

Let's check the examples:
```
irb(main):004:0> 2.is_a? Integer
=> true
irb(main):005:0> 2.is_a? Float
=> false
irb(main):006:0> 2.is_a? String
=> false
irb(main):007:0> "alexandre".is_a? Integer
=> false
irb(main):008:0> "alexandre".is_a? String
=> true
```

#### The second approach - The `class` method
*Syntax: parameter.class*
Parameter: The value that it is going to be checked
Method: class
Return: It returns the name of the class

Let's check some examples:
``` 
irb(main):009:0> 2.class
=> Integer
irb(main):010:0> 2.4.class
=> Float
irb(main):011:0> "calaça".class
=> String
irb(main):012:0> "1".class
=> String
``` 

#### The third approach - The  `===` operator
*Syntax: Class === Parameter*
Class: In this case, the `Integer` class
Approach: === (Triple equals operator)
Parameter: The value that it is going to be checked
Return: It returns true or false

Let's check some examples using the `===` (triple equals) operator
```
irb(main):001:0> Integer === 3
=> true
irb(main):002:0> Integer === "3"
=> false
irb(main):003:0> String === "alexandre"
=> true
irb(main):004:0> Array === ["calaça", "alexandre", 4]
=> true
irb(main):005:0> Array === 5
=> false
```

#### The fourth approach - The `kind_of?` method
*Syntax: parameter.kind_of?(Class)*
Parameter: The value that it is going to be checked
Method: kind_of?
Class: In this case, the `Integer` class
Return: It returns true or false

The `kind_of?` and `is_a?` methods are the same. 
Let's check the examples anyway:
```
irb(main):001:0> 1.kind_of? Integer
=> true
irb(main):002:0> 1.is_a? Integer
=> true
irb(main):003:0> 2.5.kind_of? Float
=> true
irb(main):004:0> 2.5.is_a? Float
=> true
irb(main):005:0> "alexandre".kind_of? Integer
=> false
irb(main):006:0> "alexandre".kind_of? String
=> true
irb(main):007:0> "alexandre".is_a? String
=> true
```

### Summing up:
All the 4 approaches need a parameter, which is the value that it is going to be checked.
3 of the 4 approaches return a boolean value: `kind_of?`, `is_a?` and the `===` (triple equals) operator.  The `class` method returns the name of the class.

The result can be achieved in many different ways, you can choose whatever it suits your needs.

### Conclusion
In this article, it was possible to learn and practice 4 ways to determine whether a value is a number or not in Ruby [Ready].

Hope it was useful.

That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article. 
