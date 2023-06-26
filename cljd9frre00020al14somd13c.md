---
title: "Leetcode 217. Contains Duplicate - Solution in Ruby"
datePublished: Mon Jun 26 2023 19:37:03 GMT+0000 (Coordinated Universal Time)
cuid: cljd9frre00020al14somd13c
slug: leetcode-217-contains-duplicate-solution-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/EhPih0l5bjw/upload/0fe6311d6e5a3de728a0f1fa08e48e35.jpeg
tags: interview, programming-blogs, ruby, ruby-on-rails, leetcode

---

---

### Description

Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

---

### Method structure

This is the method structure provided by Leetcode.

```ruby
# @param {Integer[]} nums
# @return {Boolean}
def contains_duplicate(nums)
  # TO do
end
```

---

### Explanation

The problem is asking you to determine whether there are any duplicate values in the given integer array nums.

If there is at least one value that appears more than once, the function should return true. However, if every element in the array is distinct (i.e., no duplicates exist), the function should return false.

---

## Solution steps

### Approach

Since there are no constraints that forbid us from using a Ruby built-in function, I think one good approach is to use the `uniq` method.

We can compare the original array with the other array after removing duplicates. If they differ, it means there are duplicates in the array.

```apache
# @param {Integer[]} nums
# @return {Boolean}
def contains_duplicate(nums)
    # todo
end
```

---

![gatinho malhado castanho e preto](https://images.unsplash.com/photo-1547045662-e5a75e7238c2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8Y2F0JTIwbWVtZXxlbnwwfHwwfHx8MA%3D%3D&w=1000&q=80 align="left")

---

### Unique elements

```apache
# @param {Integer[]} nums
# @return {Boolean}
def contains_duplicate(nums)
    nums.uniq
end
```

The operation `nums.uniq` creates a new array that contains only the unique elements from the original `nums` array.

The time complexity of this operation is `O(n)`, as it requires iterating over all elements of `nums` to identify and remove duplicates.

---

### Comparison

```apache
# @param {Integer[]} nums
# @return {Boolean}
def contains_duplicate(nums)
    nums != nums.uniq
end
```

The comparison `nums != nums.uniq` checks whether the original `nums` array is different from the array containing only the unique elements.

If the two arrays are not equal, it means there were duplicates in the original array, so, it returns true.

Otherwise, if the arrays are equal, it means there were no duplicates, and the condition evaluates to `false`.

This operation has a constant time complexity of `O(1)` because it simply compares the references of the two arrays.

---

### True or false

```apache
# @param {Integer[]} nums
# @return {Boolean}
def contains_duplicate(nums)
    nums != nums.uniq ? true : false
end
```

This comparison `nums != nums.uniq` returns true or false.

The ternary operators `?` and `:` enforce the return.

Thes ternary expression returns `true` if there were duplicates in the original array (`nums != nums.uniq` is `true`), and `false` if there were no duplicates (`nums != nums.uniq` is `false`).

---

### Final solution

```apache
# @param {Integer[]} nums
# @return {Boolean}
def contains_duplicate(nums)
    nums != nums.uniq ? true : false
end
```

---

### Complexity

This solution checks if the original array is different from the array containing only the unique elements.

The overall time complexity of the `contains_duplicate` method is determined by the time complexity of `nums.uniq`, which is `linear`, also known as `O(n)`.

Since the solution has a linear time complexity, the execution time grows linearly with the size of the input array.

---

### **Be happy**

You got here. Way to go!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome. By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---