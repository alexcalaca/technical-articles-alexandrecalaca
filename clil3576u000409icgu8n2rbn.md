---
title: "Ruby Challenge: Create a word occurrence counter"
datePublished: Wed Jun 07 2023 02:23:19 GMT+0000 (Coordinated Universal Time)
cuid: clil3576u000409icgu8n2rbn
slug: ruby-challenge-create-a-word-occurrence-counter
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Jxi526YIQgA/upload/8d7df0d2844ba22b796173a4b69c84c3.jpeg
tags: programming-blogs, ruby, coding

---

> TL; DR: Get the solution on my [Github repository.](https://github.com/alexcalaca/coding-challenges-ruby/tree/aef4d2cf0f2d26bbd8e8f8793c7a6b407fb09c3d)

---

## Problem

Create a word occurrence counter.

Given a sentence, such as the following one:

```apache
sentence = "I love Ruby, Ruby is a great language!"
```

The result would be a hash

```apache
{"I"=>1, "love"=>1, "Ruby,"=>2, "is"=>1, "a"=>1, "great"=>1, "language!"=>1}
```

---

## Steps

Let's build our solution one step at a time, so, you can grasp it.

Basically, there are 3 steps:

* Store the result;
    
* Match words;
    
* Count the words.
    

---

### Store the result

Let's start by creating a Hash object. This object is our counter.

```ruby
def count_word_occurrences(sentence)
  word_counter = Hash.new(0)
  
  return word_counter
end
```

---

### Match each word

In this step, we're going to identify and separate each word.

#### Scan method

In order to achieve this, we're going to use the `scan` method. Take a look at the following approach:

```ruby
sentence.scan(/\w+/)
```

---

#### Usage

The previous code snippet uses the `scan` method. This method is provided by the Ruby's String class. It is used to search a string (sentence in this case) for all occurrences of a specified pattern and returns an array of all matches found.

In the given code snippet, the pattern specified is `/\w+/`.

---

#### Regular expression pattern

`\w` is a metacharacter that matches any word character, which includes alphabetic characters (both uppercase and lowercase) and digits. It is equivalent to the character class \[A-Za-z0-9\_\].

The plus sign `+` is a quantifier that specifies that the preceding pattern (`\w` in this case) should be matched one or more times consecutively. Therefore, `/\w+/` matches one or more consecutive word characters.

---

#### Return

The `scan` method scans the sentence string and finds all occurrences of the pattern `/\w+/`. It then returns an array containing all the words found in the sentence.

---

#### Result

```ruby
sentence = "I love Ruby, Ruby is a great language!"

def count_word_occurrences(sentence)
  word_counter = Hash.new(0)

  # Use regular expression to match each word in the sentence
  @words = sentence.scan(/\w+/)
  
  word_counter
end

count_word_occurrences(sentence)
puts @words
```

Since we're using the `scan` method, the previous code would result in an array:

```ruby
["I", "love", "Ruby", "Ruby", "is", "a", "great", "language"]
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686066830729/7f729a04-b942-4076-91bf-93c81f3e34a5.png align="center")

---

### Count the words

As we already checked, by using the `scan` method, we got an array of words.

Now, we need to iterate through this array and check if the word element is repeated, cause if it is, we're going to add one to the `world_counter` variable:

```ruby
words.each do |word|
    word_counter[word] += 1
  end
```

The previous code is our cornerstone. Every iteration is going to add a key value to the word\_counter

```ruby
word_counter[word]
```

And add 1 to the word\_counter if the word is repeated:

```ruby
word_counter[word] += 1
```

---

## Complete solution

### Code

```apache
sentence = "I love Ruby, Ruby is a great language!"

def count_word_occurrences(sentence)
  word_counter = Hash.new(0)
  
  words = sentence.scan(/\w+/)

  words.each do |word|
    word_counter[word] += 1
  end
  
  word_counter
end

puts count_word_occurrences(sentence)
```

### Github repository

Take a look at it [here](https://github.com/alexcalaca/coding-challenges-ruby/tree/aef4d2cf0f2d26bbd8e8f8793c7a6b407fb09c3d).

---

### **Be happy**

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's get to know each other**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.