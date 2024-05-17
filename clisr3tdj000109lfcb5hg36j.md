---
title: "How to create a super simple authentication system in Ruby on Rails without devise [log in]"
datePublished: Mon Jun 12 2023 11:08:28 GMT+0000 (Coordinated Universal Time)
cuid: clisr3tdj000109lfcb5hg36j
slug: how-to-create-a-super-simple-authentication-system-in-ruby-on-rails-without-devise-log-in
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686568058359/fe4cc9d1-dfde-4f41-8b40-d8a2e76d1cda.png
tags: programming-blogs, ruby, web-development, ruby-on-rails, 2articles1week

---

---

## Problem

How to create a super simple authentication system in Ruby on Rails without devise. This article is going to focus on the login functionality.

---

## Situation

Authenticating users helps ensure that only authorized individuals can access certain features or protected resources.

While Rails provides the popular Devise gem for handling authentication, there may be scenarios where you prefer a lightweight solution or want to understand the underlying mechanics.

In this article, we will explore how to create a super simple authentication system in Ruby on Rails without relying on the Devise gem.

To be more specific, we are going to focus on the login activity.

---

## Solution

* Configure users;
    
* Configure a place to be redirected to;
    
* Manage user in the session;
    

---

## User

### Create user

```apache
bin/rails generate scaffold User name:string password:digest
```

By using the scaffold generator, you can quickly generate a basic CRUD interface for the User model, including database migration, model code, controller code, views, and tests. This scaffolding serves as a starting point for building a fully functional user management system in your Rails application.

---

### Perform migration

```apache
bin/rails db:migrate
```

---

### Install bcrypt

Uncomment the following line

```apache
gem 'bcrypt', '~> 3.1.7'
```

and run

```apache
bundle install
```

The \`bcrypt\` gem is a Ruby implementation of the \`bcrypt\` password hashing algorithm. It provides a secure way to store and verify passwords in a hashed format.

The gem automatically generates a unique salt for each password digest. Salting adds an extra layer of security by making each password hash unique, even if two users have the same password.

---

## Admin (Optional)

This step is optional. I'm going to generate an AdminController.

This controller and view are going to be reached when the user is logged in.

---

### Generate controller

```apache
rails generate controller Admin index
```

As you already know, the rails generate controller command touches:

* A view file based on the action's name;
    
* A controller;
    
* A css file;
    
* A helper file;
    
* A route.
    

---

### Index admin view page

```apache
# app/views/admin/index.html.erb
<h1>Welcome</h1>
<p>
It's <%= Time.now %>
```

---

### Index admin action

```apache
# app/controllers/admin_controller.rb
class AdminController < ApplicationController
  def index
  end
end
```

---

## Authentication Approach

In order to accomplish our super simple authentication system, we're going to choose sessions.

There are a lot of other options out there, however, this article is going to focus on Sessions.

---

## Controller

---

### Generate the controller

```ruby
bin/rails generate controller Sessions new create destroy
```

The `new` action is responsible for rendering the login form. It displays the form where users can enter their email and password to authenticate.

The `create` action is responsible for processing the login form submission. It retrieves the user's email and password from the form parameters and attempts to authenticate the user.

The `destroy` action is responsible for logging out the user and clearing their session. It removes the `user_id` from the session to mark the user as logged out.

By implementing these actions, the `SessionsController` handles the authentication process by allowing users to log in (new and create actions) and log out (destroy action).

output

```ruby
create  app/controllers/sessions_controller.rb
       route  get 'sessions/new'
              get 'sessions/create'
              get 'sessions/destroy'
      invoke  erb
      create    app/views/sessions
      create    app/views/sessions/new.html.erb
      create    app/views/sessions/create.html.erb
      create    app/views/sessions/destroy.html.erb
      invoke  test_unit
      create    test/controllers/sessions_controller_test.rb
      invoke  helper
      create    app/helpers/sessions_helper.rb
      invoke    test_unit
      invoke  assets
      invoke    scss
      create      app/assets/stylesheets/sessions.scss
```

---

### Name routes

```ruby
# config/routes.rb
controller :sessions do
  get    'login'  => :new
  post   'login'  => :create
  delete 'logout' => :destroy
end
```

This code block in the `config/routes.rb` file defines routes for the SessionsController using the `controller` method. The `controller` method allows you to group multiple routes under a specific controller.

By using the `controller` method, the routes for the SessionsController are defined concisely, indicating the HTTP method and the corresponding action in the controller. This approach follows the convention of the RESTful routing in Rails, where specific URLs map to specific actions in a controller.

---

## Login

---

### Login form

```apache
# app/views/sessions/new.html.erb
 <%= form_tag do %>
    <h2>Please Log In</h2>
    <div class="field">
      <%= label_tag :name, 'Name:' %>
      <%= text_field_tag :name, params[:name] %>
    </div>

    <div class="field">
      <%= label_tag :password, 'Password:' %>
      <%= password_field_tag :password, params[:password] %>
    </div>

    <div class="actions">
      <%= submit_tag "Login" %>
    </div>
  <% end %>
```

The `form_tag` method generates an HTML form tag. In this case, since no specific URL is provided, the form will submit to the same URL that rendered the view. The form will use the default HTTP method, which is `POST`.

The code generates a login form with two fields: one for the name/email and another for the password. The user can enter their credentials and click the "Login" button to submit the form.

---

### Implement login

```ruby
# app/controllers/sessions_controller.rb
def create
    user = User.find_by(name: params[:name])
    if user.try(:authenticate, params[:password])
      session[:user_id] = user.id
      redirect_to admin_url
    else
      redirect_to login_url, alert: "Invalid user/password combination"
    end
end
```

The `create` action in the SessionsController handles the login process.

It retrieves the user based on the provided name/email, attempts to authenticate the user using their password, and either grants access by setting the user ID in the session or redirects back to the login page with an error message.

The `authenticate` method is typically provided by the `has_secure_password` feature in Rails, which automatically adds password encryption and authentication functionality to the User model.

---

## Logged user

---

### Retrieve logged user

```apache
# app/controllers/application_controller.rb
class ApplicationController < ActionController::Base
  helper_method :current_user
  
  private

  def current_user
    @current_user ||= User.find_by(id: session[:user_id])
  end
end
```

The `current_user` method in the `ApplicationController` is a helper method that provides access to the currently logged-in user throughout the application.

The `helper_method` declaration makes the `current_user` method available in the view templates as well. By using `helper_method`, the method can be accessed from both controllers and views.

By having the `current_user` method available in the `ApplicationController`, other controllers and views can call this method to access information about the currently authenticated user. It is commonly used to implement authentication checks, authorization logic, and personalization based on the logged-in user's data.

---

### Show logged user

```apache
# app/views/layouts/application.html.erb
<% if current_user %>
    Logged in as <%= current_user.name %>
    <%= link_to 'Logout', logout_path, method: :delete %>
<% else %>
    <%= link_to 'Login', login_path %>
<% end %>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686454500124/45fc5f21-1c41-4e16-96ab-3b4343b28a6b.png align="center")

---

## Test

### Create a new user

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686454244934/10b027e8-54fc-4952-9f82-82c109bf42e1.png align="center")

---

### Log in

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686454296079/93fdda49-0f96-446c-95fa-d42a74895084.png align="center")

---

### User logged in

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686454470486/69052b11-9d23-4de4-ad4d-f3425cf6b4da.png align="center")

---

## **Celebrate**

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

## **Let's become business friends**

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

---