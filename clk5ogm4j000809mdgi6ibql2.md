---
title: "Mastering falsy values in Ruby: A step-by-step guide"
datePublished: Sun Jul 16 2023 16:55:09 GMT+0000 (Coordinated Universal Time)
cuid: clk5ogm4j000809mdgi6ibql2
slug: mastering-falsy-values-in-ruby-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689473334170/fbdfc7fb-9fa6-4ddd-91e1-dfa3b5d8de06.png
tags: programming-blogs, ruby, web-development, ruby-on-rails, developer

---

> ---
> 
> TL; DR: There are only two falsy values in Ruby: `false` and `nil`.
> 
> ---

## Falsy values

`Falsy values` are values that are considered false when evaluated in a Boolean context.

In other words, they are non-Boolean values that are treated as if they were Boolean false when used in conditional statements or expressions, and they can lead to unexpected behavior if not handled properly.

---

## Boolean context

A Boolean context refers to a situation in programming where a value or expression is evaluated in terms of its truthiness or falsiness.

In a Boolean context, the value is used as a condition to determine whether a particular block of code should be executed or not. Most programming languages support Boolean data types, which can only have two possible values: `true` or `false`.

---

## Non-boolean values

Non-Boolean values, also known as non-Boolean data types, are data types in programming languages that are not directly associated with the Boolean data type.

Unlike Booleans, which can only have two values (`true` or `false`), non-Boolean data types can represent a wide range of values, such as numbers, strings, objects, arrays, and more.

These data types serve various purposes in programming and are essential for performing different operations and storing different kinds of data.

---

## Truthiness or Falsiness

Truthiness and falsiness are concepts in programming that refer to how non-Boolean values are evaluated in a Boolean context.

In other words, it's about how values of different data types are automatically coerced into their Boolean representation (`true` or `false`) when used in situations that expect a Boolean expression, such as conditional statements, predicate methods or loops.

---

### **Truthiness**

A value is considered truthy if it evaluates to `true` in a Boolean context. Any value that is not explicitly falsy is considered truthy.

---

### **Falsiness**

A value is considered falsy if it evaluates to `false` in a Boolean context.

---

### Determining Falsiness

In order to determine falsiness in Ruby, many different approaches can be used.

Let's check two excellent approaches: ternary operator and the bang operator.

---

#### Ternary operator

The ternary operator, also known as the conditional operator, is a concise way to write conditional expressions in various programming languages, including Ruby.

It allows you to evaluate a condition and return one of two values based on whether the condition is true or false.

Let's take a look at the syntax:

```apache
condition ? value_if_true : value_if_false
```

Let's think about one example, let's check if an empty array is a truthy or a falsy value in Ruby.

```apache
# 
[] ? "Truthy" : "Falsy"
```

The previous method is going to return "Truthy", so, `[]` is a truthy value.

```apache
irb(main):011:0> [] ? "Truthy" : "Falsy"
=> "Truthy"
irb(main):012:0>
```

---

#### Bang

In Ruby, the exclamation mark (!) is often referred to as the "bang" character. It is used in various contexts, serving different purposes.

One of the purposes is **Negation or Logical NOT Operator.** In Boolean expressions, it is used in that way. It negates the truthiness of a value.

For example, let's check if an empty string is truthy or falsy.

```apache
!""
```

The previous code snippet is going to return `false`, because `""` is a `truthy` value. When used as a logical not operator, the bang is going return `true` is the expression is false.

```apache
irb(main):001:0> !""
=> false
irb(main):002:0"
```

One possibility is to use double bang, in this case, it's going to return the exact truthiness or falsiness value.

```apache
!!""
```

```apache
irb(main):002:0> !!""
=> true
```

---

## Super "big" list of Falsy values in Ruby

There are only two falsy values in Ruby:

* false;
    
* nil;
    

So, the following values are considered truthy:

* 0;
    
* "";
    
* \[\];
    
* {};
    

---

## **Celebrate**

You have learned a lot. Time to celebrate!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's connect**

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