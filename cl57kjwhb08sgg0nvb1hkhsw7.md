## Ruby: How to convert a string to uppercase?


### Greetings
Hey, It's AC (Alexandre Calaça) here. Hope you're good. Let's get down to business. Shall we?

### Introduction
Today, let's learn and practice how to convert a string to uppercase in Ruby.

### Solution
In Ruby, the `upcase` method is used to convert a string to uppercase.

The `upcase` method is immutable, it means it returns a copy of self (current object) with all characters uppercased, so, just to be clear, the original string stays the same.

The mutable version is used with a bang sign at the end, `upcase!`

### Syntax
`"my_string".upcase`

In this case, `my_string` is the string we are interested to uppercase.

### Parameters
The `upcase` method doesn't require any parameters.

### Return value
Since it is an immutable method, it returns a new uppercased string of the caller. If no conversion is necessary, it returns the unchanged original string.

Again, it's possible to return and modify self (current caller) if we use the bang operator after the method: `upcase!`.

### Coding time
Let's go over the examples.
```
irb(main):001:0> my_string = "alexandre"
irb(main):002:0> my_string.upcase
=> "ALEXANDRE"
irb(main):003:0> my_string
=> "alexandre"
```

In the previous examples, it's noticeable that:
- The `upcase` method doesn't modify the original string;
- It returns a new uppercased string of the caller;

---

```
irb(main):006:0> my_new_string = "ALEXANDRE CALACA"
irb(main):007:0> my_new_string.upcase
=> "ALEXANDRE CALACA"
```

it's possible to see that:
- The `upcase` method returns the same string if no conversion is necessary.

---

```
> my_string = "AlExAnDRe CalACa"
=> "AlExAnDRe CalACa" 
> my_string.upcase
=> "ALEXANDRE CALACA" 
> my_string
=> "ALEXANDRE CALACA" 
```
The bang operator allows the `upcase` method to modify self.

### Errors
- _NoMethodError_ <br/>
If the method is not used with a String object

```
2.7.3 :026 > array.upcase
NoMethodError (undefined method `upcase' for [1, 2, 3]:Array)
2.7.3 :027 > 4.upcase
NoMethodError (undefined method `upcase' for 4:Integer)
```

- _ArgumentError_ <br/>
If it's provided unnecessary arguments.

```
2.7.3 :028 > my_string
 => "ALEXANDRE CALACA" 
2.7.3 :029 > my_string.upcase("test")
ArgumentError (invalid option)
``` 

###  Conclusion
In this article, it was possible to learn and practice how to convert a string to uppercase in Ruby. There  are excellent examples.

That's all for today. Reach me out if you have any questions, guys.

