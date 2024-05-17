---
title: "Singleton Methods in Ruby"
datePublished: Fri May 17 2024 00:53:51 GMT+0000 (Coordinated Universal Time)
cuid: clw9yv1r3000008l7cg9leixh
slug: singleton-methods-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/g2aX18GgTT4/upload/52dc6b1d0f37b44d374761df45c333a9.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## Singleton method

### Definition

A `singleton method`, in the context of object-oriented programming, is a method that is defined for a single instance (or object) of a class rather than for the class as a whole.

It's called "singleton" because it belongs to a single instance of the class, rather than being shared among all instances.

> A `singleton method` is a method that is defined for a single object rather than a class. This means that the method is only available to that particular object and not to other instances of the same class.

---

### Ruby

As we said, a `singleton method` belongs to a specific instance of a class, rather than being shared among all instances.

In order to implement a `singleton method` in Ruby, it's necessary to use the object's name, followed by `.`(dot) and choose a method name.

It'll look something like `obj.method_name`.

---

### Implementation

```ruby
obj = Object.new

def obj.my_singleton_method(value)
  puts "#{value} comes from the singleton method in #{self}"
end

obj.my_singleton_method('Hello')
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715906794461/b11307b4-a7c8-4d78-a3bb-3b01e4ef56fe.png align="center")

In the previous example, the `my_singleton_method` is defined only for the `obj` instance, and it won't be available for other instances of the same class.

---

### Unavailable for other instances

```ruby
obj = Object.new
obj2 = Object.new

def obj.my_singleton_method(value)
  puts "#{value} comes from the singleton method in #{self}"
end

obj.my_singleton_method('Hello')
obj2.my_singleton_method('Hello')
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715906882334/35f94abb-5f9f-49ea-9f07-65b5ad1d971c.png align="center")

In case you try to use `my_singleton_method` on a another object, you'll get an `undefined method`.

---

## **Done**

---

### Conclusion

By following these steps, you can easily visualize how singleton methods work in Ruby.

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---