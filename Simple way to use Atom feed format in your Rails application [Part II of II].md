---
title: "Simple way to use Atom feed format in your Rails application [Part II of II]"
datePublished: Wed May 31 2023 10:30:42 GMT+0000 (Coordinated Universal Time)
cuid: clibkh0mz03auvrnvfj3707ml
slug: simple-way-to-use-atom-feed-format-in-your-rails-application-part-ii-of-ii
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/6vEqcR8Icbs/upload/20b2c2635aaf2765c9f0d05f9d921114.jpeg
tags: programming-blogs, ruby, ruby-on-rails, 2articles1week, crazyblogger

---

---

## Problem

How to use Atom feed format in your Rails application.

Click here if you just want to check the theory part.

---

## Introduction

In today's interconnected world, content distribution plays a vital role in keeping users engaged and informed. As a Rails developer, you're constantly seeking ways to deliver content seamlessly to your application's users.

One powerful solution that can revolutionize the way you share and distribute data is the Atom feed format. With its standardized structure and compatibility across platforms, Atom feeds provide a streamlined approach to content syndication.

---

## Objective

In this article, we will delve into the world of Atom feeds and explore how you can effortlessly integrate them into your Rails application.

---

## Feed

A "feed" refers to a format or mechanism used to distribute and deliver regularly updated content to users. It enables users to subscribe to and receive updates from websites, blogs, podcasts, or other online platforms in a standardized and structured manner.

---

## Atom

### Definition

Atom is a widely adopted XML-based feed format used for content syndication and distribution on the web. It is an open standard maintained by the Internet Engineering Task Force (IETF) and designed to provide a standardized format for publishing and subscribing to regularly updated content.

---

## Solution

The following steps were applied in the following environment;

```apache
Rails 6.0.6.1
ruby 2.7.2p137
Deepin OS 20.7.1
```

---

### Fetching the product

```ruby
# app/controllers/products_controller.rb
def who_bought
    @product = Product.find(params[:id])
    @latest_order = @product.orders.order(:updated_at).last
    if stale?(@latest_order)
        respond_to do |format|
            format.atom
        end
    end
end
```

This action retrieves the orders associated with the `@product` instance variable and orders them by their updated\_at timestamp in ascending order.

We check if `@latest_order` is considered stale. The stale? method is a built-in Rails method that helps in implementing HTTP caching and conditional GET request.

It helps determine whether the response should be re-rendered or if the client's cached version is still valid.

By adding `format.atom`, we cause Rails to look for a template named `who_bought.atom.builder`.

---

### Create atom builder template

```ruby
#app/views/products/who_bought.atom.builder
atom_feed do |feed|
  feed.title "Who bought #{@product.title}"

  feed.updated @latest_order.try(:updated_at) 

  @product.orders.each do |order|
    feed.entry(order) do |entry|
      entry.title "Order #{order.id}"
      entry.summary type: 'xhtml' do |xhtml|
        xhtml.p "Shipped to #{order.address}"

        xhtml.table do
          xhtml.tr do
            xhtml.th 'Product'
            xhtml.th 'Quantity'
            xhtml.th 'Total Price'
          end
          order.line_items.each do |item|
            xhtml.tr do
              xhtml.td item.product.title
              xhtml.td item.quantity
              xhtml.td number_to_currency item.total_price
            end
          end
          xhtml.tr do
            xhtml.th 'total', colspan: 2
            xhtml.th number_to_currency \
              order.line_items.map(&:total_price).sum
          end
        end

        xhtml.p "Paid by #{order.pay_type}"
      end
      entry.author do |author|
        author.name order.name
        author.email order.email
      end
    end
  end
end
```

It is an Atom feed template written using the Builder syntax in a Rails view file (`app/views/products/who_bought.atom.builder`). It generates an Atom feed for the `who_bought` action in the `ProductsController`

This line `atom_feed do |feed|` initializes the Atom feed and provides a block with a `feed` object for further configuration.

This code generates an Atom feed that includes information about the product, the orders associated with it, and the details of each order such as shipping address, line items, total price, payment type, and author information.

---

### Update relationships

This step is optional. It depends on your business logic.

Since I'm going to use `@product.orders`, it is necessary to have a direct relationship. In this case, I'm going to use the following snippet

```apache
# app/models/product.rb
  has_many :orders, through: :line_items
```

The class would be something like this

```apache
# app/models/product.rb
class Product < ApplicationRecord
  has_many :line_items
  has_many :orders, through: :line_items
end
```

By adding `has_many :orders, through: :line_items`, it establishes a direct association between the `Product` and `Order` models. It allows you to access the orders associated with a product by traversing through the `line_items` table.

For example, if you have a `Product` instance called `product`, you can access its associated orders using `product.orders`. This will return a collection of `Order` instances related to that specific product through the intermediate `LineItem` model.

This association simplifies querying and accessing orders associated with a product without explicitly referencing the `LineItem` model. It provides a convenient way to navigate the relationship between products and orders in your application.

This command `through: :line_items` specifies that the association between `Product` and `Order` is achieved through the `line_items` table or model. It indicates that there is an intermediate model (`LineItem`) that connects `Product` and `Order` indirectly.

---

### Change routes

```apache
#config/routes.rb
resources :products do
  get :who_bought, on: :member
end
```

The line `get :who_bought, on: :member` adds a custom route for the `who_bought` action to the `products` resource. It specifies that the route should be accessible on a member-level, meaning it will be a route that operates on a specific member (specific product) rather than the collection as a whole.

To be more specific, `on: :member` specifies that this route should be associated with a specific member (product) rather than the entire collection. It means the route will have a URL pattern that includes the product's identifier, such as `/products/:id/who_bought`.

Wrapping up, by including this route configuration, Rails will generate a route and corresponding URL helper methods for the `who_bought` action, allowing you to generate URLs and handle requests to `/products/:id/who_bought`. The `:id` parameter represents the identifier of the specific product.

For example, if you have a product with an ID of 2, you can access the `who_bought` action for that product using the URL `/products/2/who_bought`. This route would map to the appropriate controller and action, allowing you to handle and respond to requests made to that URL.

---

### Test it

```ruby
curl --silent http://localhost:3000/products/2/who_bought.atom
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685234002564/b5ae06d0-1961-4185-882f-d65378f99d2d.png align="center")

The command `curl --silent http://localhost:3000/products/2/who\_bought.atom` is a cURL command executed in a terminal. It makes a GET request to a local Rails application running on localhost at port 3000.

`curl` is a command-line tool used for making HTTP requests. When `--silent (or -s)` is used, it suppresses the progress output, making the command silent.

From the endpoint `/products/2/who\_bought.atom`, the command is requesting the Atom feed for the who\_bought action of the ProductsController for the product with an id of 2.

---

## Celebrate

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

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
