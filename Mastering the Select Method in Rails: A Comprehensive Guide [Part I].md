---
title: "Mastering the Select Method in Rails: A Comprehensive Guide [Part I]"
datePublished: Fri Apr 28 2023 16:11:02 GMT+0000 (Coordinated Universal Time)
cuid: clh0r3kz5000i09lf7c6y6pzz
slug: mastering-the-select-method-in-rails-a-comprehensive-guide-part-i
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/aG8iIT9_iqM/upload/64692ee3a97f86f197a653eebefd123a.jpeg
tags: programming-blogs, ruby, ruby-on-rails, tips

---


### Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. Hope you enjoy this new article.

By the way, I would be glad to receive your feedback about it.

---

### Introduction

This article `Mastering the Select Method in Rails: A Comprehensive Guide - Part I`  focuses on how to use the Active Record Select method.

It's important to remember that the `select` method can also be used as an Array class method (Array#select).

So, just to make sure we're on the same page, this article is not going to cover about how to use the Array#select method.


---

### The Select Method

The `select(*fields) public` method behaves in two distinct ways: one as an Array class method (`Array#select`) method, the other one as a `ActiveRecord::QueryMethods`.

In Rails, the select method is used to retrieve a collection of objects from the database that meet certain conditions specified in the method. This is going to become easier as you read this article.

#### Syntax

```apache
Model.select(:field)
```

or

```apache
Model.select("field")
```

As an example, considering a Product model, let's retrieve records with only the `title` field. It would look like this:

```apache
Product.select(:title)
```

or

```apache
Product.select("title")
```

We could also retrieve these records with some conditions. Take a look.

```ruby
Product.select(:name, :status).where('price < ?',  40)
```

In this case, the keyword `ẁhere` was added in order to apply our condition.

#### Parameters

If we check the source code, it's noticeable that the `select(*fields)` uses the `splat operator` in the argument section. In that case, when we provide arguments, they're going to be converted into an array.

`splat operators` might be covered later in another article. So far, we just need to understand that we can provide an array or a bunch of arguments separated by comma.

In Rails 3, the `select` method expects a single argument, which is an array of column names or SQL fragments to select. In case you want to try anyway, the error message would look something like this:

```apache
ArgumentError: wrong number of arguments (2 for 0..1)
from /home/alexandre/.rbenv/versions/2.1.6/lib/ruby/gems/2.1.0/gems/activerecord-3.2.11/lib/active_record/relation/query_methods.rb:70:in `select
```

In order to provide multiple values in Rails 3, using the select method, an array needs to be used as an argument, due to the splat operator:

```apache
Product.select(["type", "status"])
```

When you pass multiple arguments, Rails 3 interprets them as individual arguments instead of an array, hence the error message.

In Rails 4 and above, the `select` method can accept multiple arguments:

```apache
Product.select("type", "status")
Product.select(:type, :status)
```

#### Return

In a successful case scenario, a new Active Record relation is returned containing all elements for which the given block was provided.

```apache
selected_products = Product.select(:id, :name).where('price < ?',  10)
[...]
=> #<#<Class:#<ActiveRecord::Relation:0x00563b47398680>>:0x2b1da39cc340>
```

In the previous code, we would see a list of products that are cheaper than 10, only id and name fields are retrieved.

When the criteria specified in the select method are not met, the method returns an empty ActiveRecord::Relation object.

```apache
products = Product.select(:name).where('price > ?', 1.00)
=> #<ActiveRecord::Relation []>

products.empty?
=> true
```
---

### Summary

In this article, we learned how to use the `ActiveRecord::QueryMethods` select method.

We understood how the select method works differently as an Array class method (Array#select) and as a ActiveRecord::QueryMethods.

We also compared how some characteristics of the method have changed during the release of new Rails versions, especially with regards to parameters and returns.


---

### Celebrate

If you read the article, kudos! you did a great job. You can definitely celebrate!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

### Conclusion

That's all for today. Thanks for reading the article `Mastering the Select Method in Rails: A Comprehensive Guide [Part I]`.


I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.
