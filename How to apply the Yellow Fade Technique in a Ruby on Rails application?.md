---
title: "How to apply the Yellow Fade Technique in a Ruby on Rails application?"
datePublished: Thu May 25 2023 01:00:57 GMT+0000 (Coordinated Universal Time)
cuid: cli2fh7tj00030al1gpzxh7eb
slug: how-to-apply-the-yellow-fade-technique-in-a-ruby-on-rails-application
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/AaiYx5cp6zc/upload/4eb300eb2c0870c8bb8c058ff1f9576d.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails, 2articles1week

---

`Revisited on May 28th, 2023`

> TL; DR: Configure a CSS class and include it to apply the technique.

---

## Problem

In an Ajax-based application, users may complain that they are unable to see real-time updates.

An interesting approach to highlight changes made to a page via Ajax is the Yellow Fade Technique.

---

## Explanation

As I already mentioned, an interesting approach is to use the magical `Yellow Fade Technique`.

In this article, let's implement it.

---

## Review time

Before diving in, let's brush up on some important terms.

---

### Ajax

Ajax stands for "Asynchronous JavaScript and XML. It is a set of web development techniques used to create asynchronous web applications. It allows for the retrieval and exchange of data between the web browser and the server without requiring a full page reload.

Traditionally, when a user interacts with a web page, such as submitting a form or clicking a link, the entire page would reload, resulting in a delay and a disruption in the user experience.

Ajax, on the other hand, enables these interactions to occur asynchronously in the background, without reloading the entire page. This approach allows for smoother and more dynamic user experiences by updating specific parts of the page with new data or content.

---

### Yellow Fade Technique

The "Yellow Fade Technique" is a visual effect that involves fading an element's background color to yellow and then fading it back to its original color to draw the user's attention to the element.

The yellow fade effect is often used to highlight changes or updates on a web page, such as indicating a successful action, displaying a new message, or drawing attention to specific content.

It provides a subtle yet visually appealing transition that helps capture the user's attention without being overly intrusive.

To implement the yellow fade technique, fade-in and fade-out transitions are achieved by gradually adjusting the element's background color using CSS transitions or animation.

---

## Solution

In order to apply the solution, we won't need to touch any javascript file, we'll trust more on css in this case.

---

### Identify

First, it's necessary to identify what piece of code we're going to apply the `yellow fade technique`.

In my example, I'm going to use a partial called `_line_items.html.erb`. Everytime a user adds product to the cart, the mentioned partial is going to be highlited.

---

### Create the CSS class

Since `_line_items.html.erb` is the file we want to be changed, the matched CSS file is called `line_items.html.erb`.

```apache
# app/assets/stylesheets/line_items.scss
@keyframes line-item-highlight {
  0% {
    background: #8f8;
  }
  100% {
    background: none;
  }
}

.line-item-highlight {
  animation: line-item-highlight 5s;
}
```

This code is a CSS animation that creates a gradual highlight effect on an element with the class "line-item-highlight."

`Keyframes` defines the styles that an element should have at specific points during the animation. In this case, the animation has two keyframes: 0% and 100%.

At the 0% keyframe, the background color is set to #8f8, which represents a shade of green (#8f8 is equivalent to rgb(136, 255, 136)). This color creates the highlight effect.

At the 100% keyframe, the background color is set to none, effectively removing the background color. This returns the element to its default appearance.

The animation will smoothly transition the background color of the element between these two keyframes. Time is set to 5 seconds.

---

### Tell

This step is to tell Rails what item is going to be updated.

```apache
# app/controllers/line_items_controller.rb
format.js { @current_item = @line_item }
```

My complete create action code is this way:

```apache
def create
    product = Product.find(params[:product_id])
    @line_item = @cart.add_product(product)
    
    respond_to do |format|
      if @line_item.save
        format.html { redirect_to store_index_url }
        format.js { @current_item = @line_item }
        format.json { render :show, status: :created, location: @line_item }
      else
        format.html { render :new, status: :unprocessable_entity }
        format.json { render json: @line_item.errors, status: :unprocessable_entity }
      end
    end
  end
```

For the JavaScript format (`format.js`), it assigns the `@line_item` to the `@current_item` instance variable. This allows you to pass data from the server to the client-side JavaScript code for further processing or updating the UI.

This assignment is done to make the `@line_item` accessible in the corresponding JavaScript view file, in this case, `_line_item.html.erb`.

---

### Update

Apply the `line-item-highlight` class to the desired code.

```ruby
<% if line_item == @current_item %>
  <tr class="line-item-highlight">
<% else %>
  <tr>
<% end %>
  <td class="quantity"><%= line_item.quantity %></td>
  <td><%= line_item.product.title %></td>
  <td class="price"><%= number_to_currency(line_item.total_price) %></td>
</tr>
```

This code checks if the current `line_item` being rendered is the same as the `@current_item` that was passed from the controller.

If they are the same, the table row (`<tr>`) is given a CSS class of `"line-item-highlight"`, which is the CSS class set to use the Yellow Fade Technique, indicating that it is the updated or created item. Otherwise, if they are different, the table row is rendered without any additional class.

This conditional rendering allows you to visually distinguish the item that was just updated or created via an Ajax request, making it stand out from the rest of the line items displayed in the table.

---

## Test it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684975810589/f3ddffe2-eb3c-4b69-91a8-fd8bb2e6fc03.png align="center")

---

## Celebrate

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

## Let's connect

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
