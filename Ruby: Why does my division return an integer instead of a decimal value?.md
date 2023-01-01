## Ruby: Why does my division return an integer instead of a decimal value?

### Greetings
Hey,  It's Alexandre Calaça here. Hope you're fine.

### Introduction
In this article, let's check why some Ruby's divisions return an integer instead of a decimal value and figure out a way to solve this issue.

### Why does it happen?
First things first, `Ruby` respects our decision. If we decide to divide 4 by 2, the result is 2, however, if we decide to divide 5 by 3 the result is 1. Why?
5 are 3 are integer, so, the result is an integer. Ruby is savvy enough to respect our decision since we used two integers for the division.

Let's get down to business, shall we?
```
irb(main):001:0> 1.class
=> Integer
irb(main):002:0> 4.class
=> Integer
irb(main):003:0> 2.class
=> Integer
irb(main):004:0> 5.class
=> Integer
irb(main):005:0> 3.class
=> Integer
irb(main):006:0> 5 / 3
=> 1
irb(main):007:0> (5 / 3).class
=> Integer
```

### How to solve this issue?
In order to solve this issue, one of the numbers needs to be a float data type. Basically, there are three ways to deal with it:
- Convert one of the numbers to a float data type;
- Modify one of the numbers to become of a float data type;
- Use a special method for the division operation.

#### Conversion
In this case, one of the division elements needs to be converted into a float data type.

```
irb(main):003:0> 9.class
=> Integer
irb(main):004:0> 7.class
=> Integer
irb(main):005:0> 9/7
=> 1
irb(main):006:0> (9/7).class
=> Integer
irb(main):007:0> 9.to_f / 7
=> 1.2857142857142858
irb(main):008:0> 9 / 7.to_f
=> 1.2857142857142858 
```

#### Modification
In this case, one of the division elements needs to be modified to become a float.
```
irb(main):009:0> 7.class
=> Integer
irb(main):010:0> 4.class
=> Integer
irb(main):011:0> 7/4
=> 1
irb(main):012:0> (7/4).class
=> Integer
irb(main):013:0> 7.0 / 4
=> 1.75
irb(main):014:0> 7 / 4.0
=> 1.75
```

#### Usage
In this case, it needs to be used a different method: `fdiv`.

```
irb(main):015:0> 5.class
=> Integer
irb(main):016:0> 3.class
=> Integer
irb(main):017:0> 5 / 3
=> 1
irb(main):018:0> (5 / 3).class
=> Integer
irb(main):019:0> 5.fdiv(3)
=> 1.6666666666666667
```

### Conclusion
In this article, it was possible to understand why some Ruby's divisions return an integer instead of a decimal value.

We practiced 3 different ways to solve this issue as well.


That's all for today.
Reach me out if you have any questions, guys.
