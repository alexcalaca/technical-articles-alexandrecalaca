---
title: "How to limit the number of characters in a text field in Rails"
datePublished: Wed May 24 2023 17:32:27 GMT+0000 (Coordinated Universal Time)
cuid: cli1zgfxh000108l32l5p2cgh
slug: how-to-limit-the-number-of-characters-in-a-text-field-in-rails
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/FrGYMDjdg4U/upload/bb2395cf66f1ccedb8c041a5449b0f87.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails, 2articles1week

---

> TL; DR: Set the `maxlength` attribute to the desired number

## Problem

How to limit the number of characters in a text field in Rails.

---

## Explanation

The goal is to limit the number of characters a user can enter in an input text field in a Ruby on Rails form.

---

## Solution

Set the attribute `max length` to the desired number.

---

### form\_for

When using form\_for in Ruby on Rails with the default form builder, you can set the maximum length for a Text field by providing the maxlength option within the field options. Check it out:

```ruby
<%= form_for @post do |f| %>
  <%= f.text_field :content, maxlength: 500 %>
  <%= f.submit %>
<% end %>
```

---

### form\_tag

When using form\_tag in Ruby on Rails without any form builder like Simple Form, you can set the maximum length for a Text field by providing the maxlength attribute directly in the HTML tag. Here's how you can do it:

```ruby
<%= form_tag '/submit', method: :post do %>
  <%= text_field_tag :my_field, nil, maxlength: 500 %>
  <%= submit_tag 'Submit' %>
<% end %>
```

The previous `nil` value is the default value of the field.

---

### Simple form

In your form view file (e.g., app/views/products/new.html.erb), use the simple\_form\_for helper method to generate the form. Inside the form block, you can use the input helper method to create the Text field with the desired maximum length. Here's an example:

```ruby
<%= simple_form_for @post do |f| %>
  <%= f.input :content, input_html: { maxlength: 500 } %>
  <%= f.button :submit %>
<% end %>
```

---

### Solution notes

By specifying the `maxlength` option in the input helper, they will add the corresponding HTML attribute to the generated input field. This attribute enforces the maximum length on the client-side, preventing the user from entering more characters than allowed.

However, it's important to note that client-side validation can be bypassed, so you should also add server-side validations to ensure data integrity.

---

## Let's become friends

* [Github](https://github.com/alexcalaca)
    
* [LinkedIn](https://linkedin.com/in/alexandrecalacaofficial)
    
* [Hashnode](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [Youtube](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## Final thoughts

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---
