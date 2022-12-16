## Using a ruby method to return the absolute value of a number

What's up, guys? 

### Intro
Today, I want to share with you how to use a ruby method to return the absolue value of an integer value in Ruby.


### What's an absolute value?
I'm not a math geek, but this answer is kinda simple. The absolute value of a number x is its non-negative version, so, it's the number without the negative sign.

For example, the absolute value of the number -4 is 4. The absolute value of the positive 4 is also 4. It doesn't matter the parameter, the absolute value is always the positive version.

### Using the `abs` method
#### Definition
The `abs` belongs to the `numeric` class. In Ruby, the numeric class is the highest-level class for numbers. 

The `abs` method returns the absolute value of a given number.

The `magnitude` method is an alias for the `abs` method.

#### Syntax
The syntax is very simple:
``` 
number.abs
``` 
`number` is the value we want to check the absolute version.
`.` is how we call the method.
`abs` is the method.

#### Get down to business
Let's check it out:
```
irb(main):006:0> -9.abs
=> 9
```
The absolute value of a positive number is the number itself
```
irb(main):005:0> 9.abs
=> 9
```

Since The `abs` method also works with the float type:
```
rb(main):007:0> -3.4.abs
=> 3.4
irb(main):008:0> 3.4.abs
=> 3.4
```

A `NoMethodError` is displayed if it's used with a data type that it doesn't inherit from the `numeric class`.
```
irb(main):009:0> "1".abs
Traceback (most recent call last):
        4: from /usr/local/bin/irb:23:in `<main>'
        3: from /usr/local/bin/irb:23:in `load'
        2: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        1: from (irb):9
NoMethodError (undefined method `abs' for "1":String)
``` 

#### Summing up:
- Syntax: numericvalue.abs()
- Parameter: numeric value which is to be converted to absolute value.
- Return: absolute value of the passed numeric value.

### Conclusion
In this article, it was possible to learn and practice how to get the absolute value of numbers in Ruby.

Hope it was useful.

That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article.


