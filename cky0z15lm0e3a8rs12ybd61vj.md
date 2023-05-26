---
title: "5 effective ways to add items to arrays in Ruby"
datePublished: Wed Jan 05 2022 03:18:41 GMT+0000 (Coordinated Universal Time)
cuid: cky0z15lm0e3a8rs12ybd61vj
slug: 5-effective-ways-to-add-items-to-arrays-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1641352201747/xMzk1OjGqW.png
tags: ruby, ruby-on-rails

---

`Revisited on May 25th, 2023`

Hey guys, how's it going?

### Introduction

Today, let's learn about 5 effective ways to add items to arrays in Ruby. As always, you don't need to memorize them all, however I think it's always a good idea to know that you have a wide variety of options.

---

### Introduction to Arrays

First things first, what are Arrays?

> Arrays are *ordered, integer-indexed collections of any object*.

So, it's important to remember that array items:

* can be any object;
    
* have a specific order;
    
* are indexed by integer values;
    

Got that? So, each element of an array is associated with an integer value. Just like in a lot of other programming languages, such as C and Java, the first index value starts with 0. It might sound funny, but it's possible to have negative index values, they start with -1. The index value -1 refers to the last element of the array, -2 is the second last element of the array and so on.

Example of an array

```apache
irb(main):007:0> array = [1, 'chocolate', '2', 0]
irb(main):008:0> array
=> [1, "chocolate", "2", 0]
```

---

### 5 effective ways to add items to Arrays in Ruby

The order of the items is an important characteristic of arrays in Ruby, so, it's necessary to choose where is the new item going to be.

The most common position is at the end of the array, however it's possible to insert before all other array items or at any position. To sum up, you can choose any position.

---

#### First approach - Using the push method

In the following example, the item 10 is added to the end of the array.

```apache
irb(main):001:0> array = [1, 'chocolate', '2', 0]
=> [1, "chocolate", "2", 0]
irb(main):003:0> array.push(10)
=> [1, "chocolate", "2", 0, 10]
```

In this example, the item "new item" is added to the end of the array.

```apache
irb(main):004:0> array
=> [1, "chocolate", "2", 0, 10]
irb(main):005:0> array.push("new item")
=> [1, "chocolate", "2", 0, 10, "new item"]
```

The push method also allows to insert multiple values all at once. Check it out.

```apache
irb(main):001:0> array = [1, "chocolate", "2", 0, 10, "new item"]
irb(main):002:0> array.push(2, 3)
=> [1, "chocolate", "2", 0, 10, "new item", 2, 3]
irb(main):003:0> array.push("new", "value", 10)
=> [1, "chocolate", "2", 0, 10, "new item", 2, 3, "new", "value", 10]
irb(main):004:0>
```

The `push method` returns the array itself.

```apache
irb(main):007:0> array = [1, "chocolate", "2", 0, 10, "new item", 2, 3, "new", "
value", 10]
irb(main):008:0> array.push("99")
=> [1, "chocolate", "2", 0, 10, "new item", 2, 3, "new", "value", 10, "99"]
irb(main):009:0>
```

---

#### Second approach - Using the *&lt;&lt;* method

The `<< method` also insert values at the end of the array. In String type objects, the `<< method` appends a substring to a string.

```apache
irb(main):012:0> array = [2, 1, 4, 3]
irb(main):013:0> array << 0
=> [2, 1, 4, 3, 0]
```

It's possible to add multiple values, however not all at once. If it's necessary to insert more than one value, then the `<< method` needs to be used as many times as the number of items.

```apache
irb(main):014:0> array = [2, 1, 4, 3]
irb(main):015:0> array << 0 << 1 << 2
=> [2, 1, 4, 3, 0, 1, 2]
```

In the previous example, the `<< method` was three times, because three values were inserted at the end of the array.

The `<< method` returns the array itself.

```apache
irb(main):003:0> array = [2, 1, 4, 3]
irb(main):004:0> array << 9
=> [2, 1, 4, 3, 9]
```

---

#### The third approach - Using the `unshift` method

The `unshift` method adds items to the beginning of the array.

```apache
irb(main):005:0> array = [2, 1, 4, 3]
irb(main):006:0> array.unshift(0)
=> [0, 2, 1, 4, 3]
```

The `unshift` method allows you to add multiple items at the same time.

```apache
irb(main):008:0> array = [2, 1, 4, 3]
irb(main):009:0> array.unshift(0, 1)
=> [0, 1, 2, 1, 4, 3]
```

It returns the array itself.

```apache
irb(main):008:0> array = [2, 1, 4, 3]
irb(main):009:0> array.unshift(0, 1)
=> [0, 1, 2, 1, 4, 3]
```

---

#### The fourth approach - Using the `insert` method

Syntax

```apache
array.insert(index number, array item)
```

The `insert` method allows to insert an item at any position. It can also be used to add a substring to a string.

```apache
irb(main):008:0> array = [2, 1, 4, 3]
irb(main):009:0> array.insert(2, 0)
=> [2, 1, 0, 4, 3]
```

If only one argument is passed, the method does *nothing*, it only returns the array itself.

```apache
irb(main):007:0> array = [2, 1, 4, 3]
irb(main):008:0> array.insert(4)
=> [2, 1, 4, 3]
```

Negative index number are allowed, the index value -1 refers to the last element of the array, -2 is the second last element of the array and so on.

```apache
irb(main):009:0> array = [2, 1, 4, 3]
irb(main):010:0> array.insert(-1, 0)
=> [2, 1, 4, 3, 0]
```

It's possible to add multiple values all at once. The first argument is the index number, the other ones are the values.

```apache
irb(main):011:0> array = [2, 1, 4, 3]
irb(main):012:0> array.insert(2, 1, 2)
=> [2, 1, 1, 2, 4, 3]
```

The `insert` method returns the array itself.

```apache
irb(main):008:0> array = [2, 1, 4, 3]
irb(main):009:0> array.insert(2, 0)
=> [2, 1, 0, 4, 3]
```

---

#### The fifth approach - Using the direct index

In this approach, the value is assigned to the chosen index value. No method is used here.

Syntax

```apache
array[index] = object value
```

In the following example, the value 5 is assigned to the index 4.

```apache
irb(main):004:0> array = [1, 4, 3, 2]
irb(main):005:0> array[4] = 5
irb(main):006:0> array
=> [1, 4, 3, 2, 5]
```

Using this approach, there's no return.

```apache
irb(main):004:0> array = [1, 4, 3, 2]
irb(main):005:0> array[4] = 5
```

If an index is skipped, nil values are assigned until the specific matching index. Consider an array with 4 elements, the index starts with 0 and ends with 3. If the value 0 is assigned to the index 6, then index 4 and 5 are going to have nil values.

```apache
irb(main):001:0> array = [1, 4, 3, 2]
irb(main):002:0> array[6] = 0
irb(main):003:0> array
=> [1, 4, 3, 2, nil, nil, 0]
```

---

### Conclusion

In this article, it was possible to learn 5 effective ways to add items to Arrays in Ruby. I hope this article has been useful in your development life. Thanks for dropping by.

Hope to see you soon!