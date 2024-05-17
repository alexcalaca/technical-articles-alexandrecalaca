---
title: "How to create a super basic search form in Ruby on Rails"
datePublished: Tue May 23 2023 02:04:52 GMT+0000 (Coordinated Universal Time)
cuid: clhzmvp6j000409jqh2oi9236
slug: how-to-create-a-super-basic-search-form-in-ruby-on-rails
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/eQ2Z9ay9Wws/upload/e31ac8556fafdb2043b4b10ffc57e8e5.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails, 2articles1week

---

> TL; DR: Seriously, this form implementation is incredibly simple

### Situation

How to create a super basic search form in Ruby on Rails.

The following picture is a snapshot of an example.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684764363372/3e5fed66-7e08-4056-a78b-9e0f09635d3d.png align="center")

---

### Context

Let's consider a Product model with a title attribute.

---

### Search form

```ruby
<%= form_tag('/products', method: 'get', local: true) do %>
  <%= text_field_tag(:search) %>
  <%= submit_tag("Search") %>
<% end %>
```

`form_tag` is a helper method provided by Rails for creating HTML forms.

`'/products'` is the URL or path to which the form will be submitted. The `'/products` url is due to the index route.

`local: true` is an optional parameter that specifies whether the form should be processed locally (within the same controller) or sent to a different controller for processing. In this case, local: true indicates that the form will be processed by the same controller.

---

### Search method

Add a search method to the desired model.

```ruby
# app/models/product.rb
def self.search(search)
  if search 
      where(["title LIKE ?","%#{search}%"])
  else
      all
  end
end
```

The purpose of this code is to perform a search operation on the model's associated table based on the provided search query.

If `search` does not have a value (i.e., it is nil or false), it executes the code block inside the else statement. The keyword `all` is an ActiveRecord query method that retrieves all records from the associated table.

---

### Search class method call

Add the search method inside the controller.

```ruby
# app/controllers/products_controller.rb
  def index
    @products = Product.search(params[:search])  

    respond_to do |format|
      format.html # index.html.erb
      format.json { render json: @products }
    end
  end
```

`Product.search(params[:search])` calls the search class method on the Product model, passing `params[:search]` as an argument. It performs a search operation based on the provided search query.

`params[:search]` retrieves the value of the search parameter from the request parameters. It represents the search query entered by the user.

---

### Test it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684766490124/8338fc6f-52c2-4418-9334-af9b6db8ff60.png align="center")

---

### Solution notes

This solution does not adhere to solid design principles and may not be suitable for large-scale projects, as it lacks a focus on reusability.

When working with Rails forms, it is recommended to follow best practices for enterprise projects, such as utilizing form objects, query objects, and adopting filterable approaches using solid principles.

---

### Conclusion

In conclusion, this article has demonstrated how to create a super basic search form in Ruby on Rails.

By following the step-by-step guide, you have learned the essential components and techniques needed to implement a basic search functionality in your Rails application.

---

### Let's stay connected

* [Github](https://github.com/alexcalaca)
    
* [LinkedIn](https://linkedin.com/in/alexandrecalacaofficial)
    
* [Hashnode](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [Youtube](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### Final thoughts

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---