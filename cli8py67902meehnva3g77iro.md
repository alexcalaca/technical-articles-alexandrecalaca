---
title: "Dynamic Content Delivery: Displaying Views with Ajax Requests in Ruby on Rails"
datePublished: Mon May 29 2023 10:40:42 GMT+0000 (Coordinated Universal Time)
cuid: cli8py67902meehnva3g77iro
slug: dynamic-content-delivery-displaying-views-with-ajax-requests-in-ruby-on-rails
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685059643783/6db4dfd8-e40a-4a0e-994f-4472d33f5d6b.png
tags: ruby, web-development, ruby-on-rails, 2articles1week, crazyblogger

---

> TL; DR: Redirect to a javascript file in your controller and create a brilliant javascript code.

---

## Objective

Learn **how to handle Ajax requests in Ruby on Rails controllers** and gain a solid understanding of the fundamental concepts of Ajax in Rails.

---

## Introduction

In today's fast-paced web development landscape, delivering a seamless user experience is paramount. Users expect interactive and dynamic content that updates in real-time without the need for page reloads.

Thankfully, Ruby on Rails, a robust web framework, offers a powerful tool called Ajax (Asynchronous JavaScript and XML) that empowers developers to achieve precisely that.

---

## Ajax

Ajax (Asynchronous JavaScript and XML) is a set of web development techniques used to create asynchronous web applications. It allows for the retrieval and exchange of data between the web browser and the server without requiring a full page reload.

Traditionally, when a user interacts with a web page, such as submitting a form or clicking a link, the entire page would reload, resulting in a delay and a disruption in the user experience.

Ajax, on the other hand, enables these interactions to occur asynchronously in the background, without reloading the entire page. This approach allows for smoother and more dynamic user experiences by updating specific parts of the page with new data or content.

Ajax combines several existing technologies to achieve its functionality. By leveraging Ajax, web developers can build more interactive and responsive web applications.

---

## Solution

### 1- Set up your Rails application

Make sure you have a working Rails application with the necessary controllers, views, and routes.

---

### 2- Include the jQuery library

Ajax in Rails typically relies on jQuery, so include it in your application. You can add the following line to your `app/assets/javascripts/applicatoin.js` file:

```apache
//= require jquery
```

---

### 3-Send an Ajax request

```apache
#app/views/store/index.html.erb
<%= button_to 'Add to Cart',
    line_items_path(product_id: product),
    remote: true %>
</div>
```

In Rails, the `remote: true` option is used to enable Ajax (Asynchronous JavaScript and XML) requests for form submissions or links. When you specify `remote: true` in a form or link, it instructs Rails to send the request asynchronously using JavaScript instead of the traditional synchronous request/response cycle.

When `remote: true` is used, Rails automatically includes the necessary JavaScript libraries (like jQuery or Rails UJS) and adds the appropriate event listeners to handle the Ajax requests.

By leveraging `remote: true`, you can enhance user experience by making your application more responsive and interactive, as it allows you to update specific portions of the page without a full page reload.

---

### 4 - Redirect to javascript

```apache
#app/controllers/line_items_controller.rb
def create
    product = Product.find(params[:product_id])
    @line_item = @cart.add_product(product)
    
    respond_to do |format|
      if @line_item.save
        format.html { redirect_to store_index_url }
        format.js
        format.json { render :show, status: :created, location: @line_item }
      else
        format.html { render :new, status: :unprocessable_entity }
        format.json { render json: @line_item.errors, status: :unprocessable_entity }
      end
    end
  end
```

The `format.js` within a Rails controller action is used to handle and respond to Ajax requests that expect a JavaScript response. It allows you to define the behavior when the request is made with a JavaScript format.

In a Rails controller, you typically have actions that respond to different formats, such as HTML, JSON, or JavaScript. The `format.js` block is used to handle the JavaScript format specifically.

---

### 5- Create the method

```apache
touch create.js.erb
```

Typically, you use a corresponding `.js.erb` view file to render JavaScript responses. This view file can contain JavaScript code that will be executed when the response is received.

Since our example is with the create action, our corresponding file is `create.js.erb`. If you don't write the name correctly, you might run into an error:

```apache
No template found for LineItemsController#create, rendering head :no_content
```

By using `format.js` and the corresponding `.js.erb` view file, you can control the behavior of your Rails application when responding to Ajax requests made with a JavaScript format, enabling dynamic updates and interactions on the client-side.

---

### 6-Implement

```apache
#app/views/line_items/create.js.eb
cart = document.getElementById("cart")
cart.innerHTML = "<%= j render(@cart) %>"
```

`- cart = document.getElementById("cart")`

This line retrieves an element from the DOM with the ID "cart" and assigns it to the variable `cart`. It uses JavaScript's `getElementById` method to select the element.

`- cart.innerHTML = "<%= j render(@cart) %>"`

This line updates the HTML content inside the `cart` element. The `innerHTML` property of an element represents its content as HTML.

The content to be updated is the result of `<%= j render(@cart) %>`. Here, `render(@cart)` is a Rails view rendering method that generates HTML for the `@cart` object. The `j` method is used to escape the rendered HTML to prevent any potential JavaScript injection attacks.

The generated HTML is then assigned to the `innerHTML` property of the `cart` element, effectively replacing its existing content with the new HTML representation of the `@cart` object.

---

### Test it

---

## Celebrate

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

## **Let's get to know each other**

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