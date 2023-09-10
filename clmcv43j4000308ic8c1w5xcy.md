---
title: "How to install and configure action_text in a Ruby on Rails 6 application"
datePublished: Sun Sep 10 2023 02:55:10 GMT+0000 (Coordinated Universal Time)
cuid: clmcv43j4000308ic8c1w5xcy
slug: how-to-install-and-configure-actiontext-in-a-ruby-on-rails-6-application
tags: tutorial, ruby, web-development, ruby-on-rails

---

---

## Definition

Action Text is a feature introduced in Ruby on Rails version 6.0 and later that makes it easy to handle rich text content in web applications.

It provides a framework for integrating a WYSIWYG (What You See Is What You Get) editor into your Rails applications for creating and editing rich text content, such as formatted text, images, and embedded multimedia.

---

## Context

---

## Install active\_storage

```apache
rails active_storage:install
rails db:migrate
```

---

### Check installation

```apache
gem list | grep activestorage
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694230394852/f3abbde5-aee4-4800-b4d9-f2513abd42fe.png align="center")

---

## Install action\_text

### Command

```apache
rails action_text:install
```

### Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694231117095/4f173c50-faec-4736-af4f-f96349021c01.png align="center")

### Explanation

The `rails action_text:install` command:

1. **Generates Migration Files:** The `rails action_text:install` command generates a migration file for creating the necessary database tables to store rich text content and its associated records. Specifically, it creates migration files for the `ActionText::RichText` and `ActiveStorage::Attachment` models.
    
2. **Modifies JavaScript and CSS Files:** It adds JavaScript and CSS imports to your application's JavaScript and CSS packs to include the required assets for Action Text. Specifically, it includes Trix, a rich text editor, and the Action Text stylesheets.
    
3. **Creates an Action Text Config File:** It generates an `action_text.rb` configuration file in the `config/initializers` directory. This file allows you to configure various aspects of Action Text, such as the rich text editor's toolbar buttons and allowed HTML elements.
    
4. **Sets Up Active Storage:** If you haven't already installed Active Storage in your application, the command will prompt you to run `rails active_storage:install`. Active Storage is used to manage file attachments in Action Text.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694309799425/dc4b0eb3-ea0f-4576-86d8-2fcf79018ae1.png align="center")

---

## Configure field

### Initial code

```plaintext
#  app/models/course.rb
has_rich_text :description
```

### Complete code

```plaintext
#  app/models/course.rb
class Course < ApplicationRecord
  validates :title, presence: true
  validates :description, presence: true, length: { :minimum => 5 }

  belongs_to :user
  has_rich_text :description
end
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694311782905/62181010-becb-4f5d-bb67-cb9fbb9513e3.png align="center")

### Explanation

The `has_rich_text :description` specifies that the `Course` model has a rich text attribute called `description`. This means that you can use Action Text to create and edit rich text content for the `description` attribute, allowing you to format text, add images, and perform other rich text editing operations.

---

## Create stylesheets folder

### Command

```plaintext
mkdir app/javascript/stylesheets
```

### Check creation

```plaintext
ls app/javascript/
```

#### Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694312117924/d703d61a-d185-4108-a60a-df9fbc7817db.png align="center")

---

## Create action\_text stylesheets file

### Command

```plaintext
touch app/javascript/stylesheets/actiontext.scss
```

### Check creation

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694312247308/b60f017e-cc33-4b37-82d6-8de2fca37e93.png align="center")

---

## Configure application.js

### Code

```plaintext
# app/javascript/packs/application.js
require('stylesheets/application.scss')
```

### Complete code

```plaintext
// This file is automatically compiled by Webpack, along with any other files
// present in this directory. You're encouraged to place your actual application logic in
// a relevant structure within app/javascript and only use these pack files to reference
// that code so it'll be compiled.

import Rails from "@rails/ujs"
import Turbolinks from "turbolinks"
import * as ActiveStorage from "@rails/activestorage"

import 'bootstrap/dist/js/bootstrap'
import 'bootstrap/dist/css/bootstrap'
import "bootstrap"
import 'stylesheets/index.scss';

import "channels"
import "@fortawesome/fontawesome-free/css/all"

Rails.start()
Turbolinks.start()
ActiveStorage.start()

require('stylesheets/application.scss')
require("trix")
require("@rails/actiontext")
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694314125654/a14fe3d0-cbe8-4067-bf10-4b8ac5038eb0.png align="center")

---

## Configure application.scss

### Initial code

```plaintext
# app/javascript/stylesheets/application.scss
@import 'trix/dist/trix';
@import './actiontext.scss';
```

### Complete code

```plaintext
# app/javascript/stylesheets/application.scss
@import 'trix/dist/trix';
@import './actiontext.scss';
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694314214378/c575481a-86ff-4054-bb4d-0379519ae783.png align="center")

---

## Configure form

### Initial code

```plaintext
# app/views/courses/_form.html.erb
  <%= f.label :description %>
  <%= f.rich_text_area :description %>
```

### Complete code

```plaintext
# app/views/courses/_form.html.erb
<%= simple_form_for(@course) do |f| %>
  <%= f.error_notification %>
  <%= f.error_notification message: f.object.errors[:base].to_sentence if f.object.errors[:base].present? %>

  <div class="form-inputs">
    <%= f.input :title %>    
    <%= f.label :description %>
    <%= f.rich_text_area :description %>
    <%= f.hidden_field :user_id, value: current_user.id %>    
  </div>

  <div class="form-actions">
    <%= f.button :submit %>
  </div>
<% end %>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694313742730/846234d7-8ff9-4ef8-8f71-cd3ef3a36241.png align="center")

### Check form

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694313663826/8df4f5e6-a2f1-401a-996a-742e55833f84.png align="center")

---

## Test it

### Initial

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694313663826/8df4f5e6-a2f1-401a-996a-742e55833f84.png align="center")

### Result

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694314343282/90a3b38a-0797-4115-8843-e027067cfcab.png align="center")

---

## **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article has been helpful to you. Please feel free to reach out if you have any questions. Your thoughts, suggestions, and corrections are more than welcome.

By the way, don't hesitate to drop your suggestions for new blog articles.

I look forward to seeing you next time.

---