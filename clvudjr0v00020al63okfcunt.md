---
title: "How to unrequire a Ruby module/library"
datePublished: Mon May 06 2024 03:00:40 GMT+0000 (Coordinated Universal Time)
cuid: clvudjr0v00020al63okfcunt
slug: how-to-unrequire-a-ruby-modulelibrary
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## Require

### Regular process

The process to require a module/library is by using:

```ruby
require 'objspace'
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714963358377/cb7487f3-456b-432e-b2f1-b7cc3cf1fa43.png align="center")

---

## "Unrequire"

### List all loaded features

Everytime you require a module/library in ruby, this new value is added to the `$LOADED_FEATURES` array.

In the `irb` terminal:

```ruby
$LOADED_FEATURES
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714963651560/8ad3f11b-d2e6-41bb-ada2-99a45dd1055c.png align="center")

---

### Find your module/library

Yes, you can use the `$LOADED_FEATURES` array directly to check if your module or library has been loaded.

You can do this by iterating through the array and checking if the module's name is included in any of the paths stored in `$LOADED_FEATURES`.

```ruby
$LOADED_FEATURES.any? { |path| path.include?("readline") }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714964036790/8b86bf66-4e04-45bf-9c68-22806adfef0c.png align="center")

In the previous example, `readline` is an example of a Ruby module/library.

---

### Mutate the loaded features

In Ruby, once you've required a module or library using the `require` keyword, you can't directly "unrequire" it. However, you can achieve a similar effect by removing the module from the `$LOADED_FEATURES` array.

```ruby
$LOADED_FEATURES.delete_if { |path| path.include?('benchmark') }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714964239620/d4ebcb9b-4868-4a23-aaa3-11f55ef89708.png align="center")

In my previous example, `benchmark` is the module/library.

---

### Double check the loaded features

Let's check if the `benchmark` module was removed from the `$LOADED_FEATURES` array:

```ruby
$LOADED_FEATURES.any? { |path| path.include?("benchmark") }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714964328766/b623a422-07de-4122-938c-96a6623b0440.png align="center")

---

## **Done**

---

### Conclusion

By following these steps, you can unrequire a Ruby module/library.

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