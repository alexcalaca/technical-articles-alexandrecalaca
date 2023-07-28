---
title: "Most Frequent Even Element problem - LeetCode 2404"
datePublished: Fri Jul 28 2023 15:44:59 GMT+0000 (Coordinated Universal Time)
cuid: clkmr8lyn000009jt9t80g89z
slug: most-frequent-even-element-problem-leetcode-2404
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690559054757/17603545-73f2-47a2-9526-9811f2ef75e0.png
tags: challenge, programming-blogs, ruby

---

---

## Problem

---

> Given an integer array `nums`, return *the most frequent even element*.
> 
> If there is a tie, return the **smallest** one. If there is no such element, return `-1`.

More details can be found [here](https://leetcode.com/problems/most-frequent-even-element).

---

## Explanation

Given an integer array `nums`, the goal is to find the most frequent even element in the array.

If there are multiple even elements that appear the most frequently, we need to return the smallest one.

If there are no even elements in the array, the function should return `-1`.

---

## Solution steps

Step 1: Initialize a hash to store the counts of each even element.  
Step 2: Iterate through the input array nums and count the occurrences of even elements.  
Step 3: Check if there are any even elements in the `only_evens` hash.  
Step 4: Find the most frequent even element.  
Step 5: Find the smallest one if there's a tie.  
Step 6: Return the result.

---

## Solution

### Initialize a hash

```ruby
def most_frequent_even(nums)
    only_evens = Hash.new(0)
end
```

This line `only_evens = Hash.new(0)` is really important. It initializes a new hash called `only_evens` with a default value of 0.

In Ruby, when you access a key in a hash that doesn't exist, or an array index that doesn't exist, it returns `nil` by default. However, by using `Hash.new(0)`, we specify that if a key is not found in the hash, it will return the default value 0 instead of `nil`.

By using `Hash.new(0)`, we can simplify the code and avoid the need to explicitly check whether a key exists in the hash when performing arithmetic operations, like counting occurrences.

If a key is not present, the hash will return the default value 0, making it convenient for counting occurrences or initializing counts without additional conditional checks.

---

### Count the occurrences of even elements

```ruby
def most_frequent_even(nums)
    only_evens = Hash.new(0)

    nums.each do |num|
        only_evens[num] += 1 if num.even?
    end
end
```

This loop goes through each element in the `nums` array. If the element is even, determined by `num.even?`, it increments the count of that element in the `only_evens` hash, using `num` as the hash key.

---

### Check if there are any even elements in the `only_evens` hash.

```ruby
def most_frequent_even(nums)
    only_evens = Hash.new(0)

    nums.each do |num|
        only_evens[num] += 1 if num.even?
    end

    return -1 if only_evens.empty?
end
```

If the `only_evens` hash is empty, it means there were no even elements in the original array, so we immediately return -1 as specified in the problem description.

---

### Find the most frequent even element

```ruby
def most_frequent_even(nums)
    only_evens = Hash.new(0)

    nums.each do |num|
        only_evens[num] += 1 if num.even?
    end

    return -1 if only_evens.empty?

    highest_frequency = 0
    only_evens.each do |num, frequency|
        if frequency > highest_frequency 
            highest_frequency = frequency
        end
    end
end
```

`highest_frequency` is used to keep track of the highest frequency of any even element encountered so far. It starts at 0 because we haven't found any even elements yet.

The loop `only_evens.each do |num, frequency|` is going to examine each even element and its frequency.

It iterates through each key-value pair in the `only_evens` hash, where `num` is the even element (the key), and frequency is the count of how many times it appears (the value).

The next part is to compare the current `frequency` element of the `only_evens` hash with `highest_frequency`.

If the `frequency` of the current element is greater than the `highest_frequency` seen so far, we update `highest_frequency` with the current element `frequency`.

---

### Find the smallest frequent even element

```ruby
def most_frequent_even(nums)
    only_evens = Hash.new(0)

    nums.each do |num|
        only_evens[num] += 1 if num.even?
    end

    return -1 if only_evens.empty?

    highest_frequency = 0
    smallest_frequent = nil

    only_evens.each do |num, frequency|
        if frequency > highest_frequency || (frequency == highest_frequency && num < smallest_frequent)
            highest_frequency = frequency
            smallest_frequent = num
        end
    end
end
```

This part `(frequency == highest_frequency && num < smallest_frequent)` is relevant only when the frequency of the current even element `frequency` is equal to the current highest frequency `highest_frequency`.

It further checks if the current even element `num` is smaller than the previously recorded most frequent even element `smallest_frequent`.

If `num < smallest_frequent`, it means we have found another even element with the same highest frequency as the previously recorded most frequent even element, but this new element is smaller in value.

In this case, we update `smallest_frequent` to hold the value of the current even element `num`. This ensures that we always have the smallest even element with the highest frequency stored in smallest\_frequent.

---

### Return the smallest most frequent even number

```ruby
def most_frequent_even(nums)
    only_evens = Hash.new(0)

    nums.each do |num|
        only_evens[num] += 1 if num.even?
    end

    return -1 if only_evens.empty?

    highest_frequency = 0
    smallest_frequent = nil

    only_evens.each do |num, frequency|
        if frequency > highest_frequency || (frequency == highest_frequency && num < smallest_frequent)
            highest_frequency = frequency
            smallest_frequent = num
        end
    end

    smallest_frequent
end
```

---

## RSpec tests

```apache
spec/most_frequent_even_element_spec.rb

require_relative "../lib/most_frequent_even_element"
require 'rspec'

RSpec.describe 'most_frequent_even_element' do
  subject { most_frequent_even(nums) }  

  context 'when the input array is empty' do
    let(:nums) {[]}

    it 'returns the number -1' do
      is_expected.to eq(-1)
    end
  end

  context 'when the input array has no even elements' do
    let(:nums) {[1, 9, 3, 3, 7, 5, 5]}

    it 'returns -1' do
      expect(subject).to eq(-1)
    end
    
  end

  context 'when the input array contains even elements' do
    context 'when there is only one even element' do
      let(:nums) {[8, 9, 3, 3, 7, 5, 5]}

      it 'returns the only one even element' do
        expect(subject).to eq(8)
      end
    end

    context 'when there are over two even elements' do
      let(:nums) {[4, 2, 2, 3, 7, 4, 4]}

      it 'returns the most frequent' do
        expect(subject).to eq(4)
      end
    end

    context 'when there is a tie' do
      let(:nums) {[4, 2, 2, 3, 2, 4, 4]}

      it 'returns the smallest' do
        expect(subject).to eq(2)
      end
    end    
  end
end
```

---

## Algorithm efficiency

Algorithm Efficiency Algorithm efficiency is essential for achieving faster execution, scalability, optimal resource utilization, energy efficiency, scalable system design, and gaining a competitive advantage in specific domains.

An algorithm is considered efficient when it has both low time complexity and low space complexity, allowing it to execute quickly and use minimal memory resources for various input sizes. Achieving efficiency is essential in developing high-performance software applications and systems.

---

### Time complexity

* Building the `only_evens` hash
    

The loop that iterates through the `nums` array and counts the occurrences of even elements takes `O(N)` time, where N is the number of elements in the input array `nums`.

In the worst case, we need to visit every element in `nums` once to count the even elements. So, we are talking about `linear time`.

* Finding the most frequent even element
    

The second loop that iterates through the `only_evens` hash takes O(M) time, where M is the number of unique even elements in the input array `nums`.

In the worst case, the number of unique even elements is proportional to N (all elements are unique even numbers), so this loop also takes O(N) time.

Overall, the time complexity of the solution is O(N) + O(N) = O(N), where N is the number of elements in the input array `nums`.

---

### Space complexity

`* only_evens` hash:

The space taken by the `only_evens` hash is proportional to the number of unique even elements in the input array `nums`.

In the worst case, when all elements are unique even numbers, the size of the hash will be equal to the number of elements in `nums`, so it will take O(N) space, linear time complexity.

`- highest_frequency` and `smallest_frequent`:

These variables only store single integer values, so they occupy `constant space, O(1)`.

Other variables used in the solution have negligible space compared to the input size and can be considered constant space.

the overall space complexity of the solution is `O(N)` due to the `only_evens` hash, where N is the number of elements in the input array `nums`. The rest of the variables require constant space.

---

Github

---

## **Celebrate**

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

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
