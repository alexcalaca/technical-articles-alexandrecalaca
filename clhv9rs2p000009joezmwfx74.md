---
title: "undefined local variable or method `root_path' for #<XXXController> in Rails"
datePublished: Sat May 20 2023 00:46:49 GMT+0000 (Coordinated Universal Time)
cuid: clhv9rs2p000009joezmwfx74
slug: undefined-local-variable-or-method-rootpath-for-xxxcontroller-in-rails
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/9225STV9W-M/upload/01139ad1946c0ece72dc49919cf7df5d.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails, 2articles1week

---

> TL; DR: If you specify a new name for a route, a new path is also going to be defined.

---

## Problem

Rails doesn't not redirect to `root_path`, even though there's a root route defined in the `routes.rb` file.

---

## Error

Let's check the error in several different angles.

### Full message

```ruby
undefined local variable or method `root_path' for #<XXXController:0x00007f4704ba2f50> Did you mean? XXX_path
```

### Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684468465204/02bd0043-c950-4c03-8507-d39a856c5c7f.png align="center")

### Code

```apache
      if @cart.id != session[:cart_id]      
        redirect_to root_path, alert: "Access denied."
      end
```

The previous piece of code is inside a method called `set_cart`. When the method is invoked, Rails raises that error.

### Explanation

This error message typically occurs when the root\_path helper method is not recognized within a specific controller context.

The error suggests that the `root_path` helper is being called within the XXXController, where XXX represents the name of the controller, but it is not defined or accessible in that context.

---

## Solution

### 1- Make sure you invoked the `root_path` correctly. No typos.

This snippet shows a good use of the `root_path` helper. Make sure you're using it correctly.

```apache
    if @cart.id != session[:cart_id]      
      redirect_to root_path, alert: "Access denied."
    end
```

---

### 2- Check your routes list

You can accomplish this step by using two possible approaches: the terminal or the browser.

The idea is to display the application's defined routes. This step is going to provide a list of all routes defined in the `config/routes.rb` file along with their corresponding HTTP verbs, URL patterns, controller actions, and route names.

* Browser
    
    In your browser, type the following:
    

```ruby
http://localhost:3000/routes
```

Your browser is going to render a single view page with all routes.

* Terminal
    
    First, make sure you are in the root directory of your application in the command line. Running this command will display the list of routes configured in your application.
    

In Rails 4 and earlier versions, `rake routes` is the default command. Let's check it out.

```ruby
bundle exec rake routes
```

Starting from Rails 5, the best command is the following:

```apache
rails routes
```

In Rails 6, it's possible to use the `--expanded` argument. This argument formats the routes in the screen.

```apache
rails routes --expanded
```

The result would look something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684469224620/47be0b86-1469-4f9e-a7fe-9e80b51f5dbb.png align="center")

it's possible to filter by using `grep`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684469312019/3455c337-6575-4ad5-bb6d-370c8695048d.png align="center")

---

### 3- Make sure you have a root route defined

In your `routes.rb` file, which is located inside the `config` directory, make sure you have a root route added there.

The following code is the correct form of the root route

```apache
# config/routes.rb
    Rails.application.routes.draw do
      resources :line_items
      resources :carts
      root 'store#index'
      resources :products
      # For details on the DSL available within this file, see https://guides.rubyonrails.org/routing.html
    end
```

In the previous example, the root path is going to invoke the action index of the controller store.

however, based on my real case scenario, take a look at my `config/routes.rb` file.

```apache
    # config/routes.rb
    Rails.application.routes.draw do
      resources :line_items
      resources :carts
      root 'store#index', as: 'store_index'
      resources :products
      # For details on the DSL available within this file, see https://guides.rubyonrails.org/routing.html
    end
```

Yes, the root route is defined, but I'm using a named route:

```apache
    # config/routes.rb
    [...]
      root 'store#index', as: 'store_index'
    [...]
```

---

4- Pay attention with named routes  
Basically, `named routes` are a way to give a specific name to a route defined in the application's routing configuration.

When a named route is used, a new path is created based on it.

Look at the following code again, since I used a named route for the root, my path was changed to `store_index_path`.

```apache
    # config/routes.rb
    Rails.application.routes.draw do
      resources :line_items
      resources :carts
      root 'store#index', as: 'store_index'
      resources :products
      # For details on the DSL available within this file, see https://guides.rubyonrails.org/routing.html
    end
```

In order to solve the `root_path` error, I need to remove my named route:

```apache
    # config/routes.rb
    [...]
      root 'store#index'
    [...]
```

Another option is to forget this `root_path` error and use the new generated path, which is `store_index_path`

```apache
    # config/routes.rb
    [...]
      root 'store#index', as: 'store_index'
    [...]
```

---

### 5- Test it

You can test it by checking your routes list again. If you decide to remove your named route, you should be able to see your `root_path` again.

```apache
  # config/routes.rb
    [...]
      root 'store#index'
    [...]
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684471277772/95b437a8-003b-4172-a9c6-5ebd918e3bb1.png align="center")

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
