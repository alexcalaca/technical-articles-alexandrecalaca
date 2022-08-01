## How to calculate the square root of a number in Ruby?

Hey guys,
how's it going?

It's always a pleasure to share some content and ideas with you. Hope you enjoy it.

Anyway, let's get down to business, shall we?

##Introduction

First, we need to remember that it is possible to calculate the square root of a number from scratch, which it is not the case of this post.

In order to calculate the square root of a number, we're going to use the sqrt method. We can use it from the `Math module` or the `Integer class`. ]

``` 
Integer.sqrt(parameter)
``` 

``` 
Math.sqrt(parameter)
``` 

## Syntax

```Integer class```
```
Integer.sqrt(number)```

```Math module```
```
Math.sqrt(number)```

## Parameters

The ```Integer.sqrt()``` and ```Math.sqrt()``` require a non-negative number as a parameter. The Math module is going to treat the parameter as a float type, while the Integer class as an integer type.

About the ```Integer.sqrt()```, if the parameter is not an Integer, such as a float or a string, it is going to be converted to integer first, and only after that the square root is returned.
The same process happens to the ```Math.sqrt()``` method, the parameter is going to be converted to float first.

The conversion between number is a simple case scenario, the problem is when the parameter is string.

A ```TypeError``` is returned if the parameter value is a String.
```
irb(main):006:0> Integer.sqrt('4')
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):5
        2: from (irb):6:in `rescue in irb_binding'
        1: from (irb):6:in `sqrt'
TypeError (no implicit conversion of String into Integer)
irb(main):007:0> Math.sqrt('4.0')
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):6
        2: from (irb):7:in `rescue in irb_binding'
        1: from (irb):7:in `sqrt'
TypeError (can't convert String into Float)
```

A ```Math::DomainError```  is returned if a negative value is used as a parameter.

```
irb(main):001:0> Integer.sqrt(-2)
Traceback (most recent call last):
        5: from /usr/local/bin/irb:23:in `<main>'
        4: from /usr/local/bin/irb:23:in `load'
        3: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        2: from (irb):1
        1: from (irb):1:in `sqrt'
Math::DomainError (Numerical argument is out of domain - "isqrt")
irb(main):002:0> Math.sqrt(-2)
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):1
        2: from (irb):2:in `rescue in irb_binding'
        1: from (irb):2:in `sqrt'
Math::DomainError (Numerical argument is out of domain - "sqrt")```

An ```ArgumentError```  is  returned if the given number of parameters is different than 1, since it is expected 1 parameter.
```
irb(main):010:0> Integer.sqrt
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):9
        2: from (irb):10:in `rescue in irb_binding'
        1: from (irb):10:in `sqrt'
ArgumentError (wrong number of arguments (given 0, expected 1))
irb(main):011:0> Math.sqrt
Traceback (most recent call last):
        6: from /usr/local/bin/irb:23:in `<main>'
        5: from /usr/local/bin/irb:23:in `load'
        4: from /var/lib/gems/2.5.0/gems/irb-1.1.0/exe/irb:11:in `<top (required)>'
        3: from (irb):10
        2: from (irb):11:in `rescue in irb_binding'
        1: from (irb):11:in `sqrt'
ArgumentError (wrong number of arguments (given 0, expected 1))
```



## Return value
The `Integer.sqrt()` returns the integer square root of the non-negative integer parameter, so, as an example, the largest non-negative integer square root of 5 is 2. The method returns the largest integer number.

```
irb(main):001:0> Integer.sqrt(1)
=> 1
irb(main):002:0> Integer.sqrt(2)
=> 1
irb(main):003:0> Integer.sqrt(3)
=> 1
irb(main):004:0> Integer.sqrt(4)
=> 2
irb(main):005:0> Integer.sqrt(5)
=> 2
``` 
The square root of 2 is 1.4142135623730951, but this is not an integer number, so, the `Integer class` is going to treat it as an integer, it returns the number 1.

The `Math.sqrt()` is able to return a float value.
```
irb(main):006:0> Math.sqrt(1)
=> 1.0
irb(main):007:0> Math.sqrt(2)
=> 1.4142135623730951
irb(main):008:0> Math.sqrt(3)
=> 1.7320508075688772
irb(main):009:0> Math.sqrt(4)
=> 2.0
```
## Conclusion
That's all for today.
Let me know if you have any questions. 
