---
title: "Rails 6: Webpacker::Manifest::MissingEntryError"
datePublished: Sat Mar 04 2023 02:26:45 GMT+0000 (Coordinated Universal Time)
cuid: cletcfot1000409jq1xud95m9
slug: rails-6-webpacker-manifest-missing-entry-error
tags: programming-blogs, ruby, ruby-on-rails, deepin

---

Hey guys, how have you been?

Today, we are going to learn how to solve the following error message: `Webpacker::Manifest::MissingEntryError`

To be more specific, here's the complete error message:

```ruby
Webpacker can't find application in /home/calaca/Documents/Apps/depot/public/packs/manifest.json. Possible causes:
1. You want to set webpacker.yml value of compile to true for your environment
   unless you are using the `webpack -w` or the webpack-dev-server.
2. webpack has not yet re-run to reflect updates.
3. You have misconfigured Webpacker's config/webpacker.yml file.
4. Your webpack configuration is not creating a manifest.
Your manifest contains:
{
}

```

Here's the snapshot of the app at the moment.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677869486487/3f7763cb-117b-4661-a5fd-cf42fcada6c2.png align="center")

Here is the current `Gemfile`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677870095226/93db950b-824e-4dad-a347-76d49b817dce.png align="center")

My operating system is `Deepin OS 20.7.1`, a debian-based linux distribution.

You can check yours by running the following command:

```ruby
lsb_release -a
```

### **Introduction**

#### What's webpack?

The goal of webpack, or any front-end build system, is to allow you to write your front-end code in a way that is convenient for developers and then package that code in a way that is convenient for browsers. With webpack, you can manage JavaScript, CSS, and static assets like images or fonts. Webpack will allow you to write your code, reference other code in your application, transform your code, and combine your code into easily downloadable packs.

#### When does the error happen?

It happens when we run `rails server` and we try to render a view page.

---

### **Solution**

#### **1 - Install Bootstrap 5**

```ruby
yarn add bootstrap
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677870455897/5562cff2-6e80-453e-831e-7acf6eae0719.png align="center")

---

#### **2 - Install @popperjs/core**

**Ruby**

```ruby
yarn add @popperjs/core
```

You should get something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677870686589/bea1b738-92f0-477a-8a79-f317d59717d1.png align="center")

---

#### **3 - Check if they are installed**

```apache
npm list
```

You should see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677870896087/2af76edc-18d8-4e4d-8fd3-12e782ebb383.png align="center")

---

#### **4 - Create a stylesheets folder inside javascript**

```ruby
mkdir app/javascript/stylesheets
```

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677871034367/8973095e-aaf4-4b6c-9788-60393f706d27.png align="center")

---

#### **5 - Create the main stylesheets file of the app**

```ruby
touch app/javascript/stylesheets/application.scss
```

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677871205114/7bb5d23e-725e-4c4d-affa-fb53dd0f9bf0.png align="center")

---

#### **6 - Reference CSS**

```ruby
#app/views/layouts/application.html.erb
<%= stylesheet_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677871413133/aa44b034-fe56-4750-b7e4-708ef78c3c99.png align="center")

The `Method: Webpacker::Helper#stylesheet_pack_tag` creates link tags that reference the css chunks from entrypoints when using split chunks API, as compiled by webpack per the entries list in package/environments/base.js. By default, this list is auto-generated to match everything in app/packs/entrypoints/\*.js and all the dependent chunks. In production mode, the digested reference is automatically looked up.

---

#### **7 - Import main css file inside application.js**

```ruby
#app/javascript/packs/application.js
import "stylesheets/application"
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677871614208/dadec25a-fdfc-4d5b-a96e-60f9528f851e.png align="center")

---

#### **8 - Add bootstrap 's libraries**

```ruby
#app/javascript/packs/application.js
import "bootstrap/dist/js/bootstrap"
import "bootstrap/dist/css/bootstrap"
```

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677871907318/991d3ed6-d83c-45d4-a060-fac91b40cd4a.png align="center")

---

#### **09 - Add webpacker rails**

```ruby
yarn add @rails/webpacker
```

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677872085905/19875ee2-f54e-4fa3-b697-af0f3b6108b3.png align="center")

...

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677872107877/90fbd5bf-cd5a-4399-8b5f-c286b7f50c4d.png align="center")

...

---

#### **10 - Check your npm list**

```ruby
npm list
```

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677872153509/1d6e597e-ff02-4408-bca2-1e56c248cd4e.png align="center")

---

#### **11 - Test it**

Run the server

```ruby
rails server
```

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677872370198/d6eb0273-408b-409b-b43e-8d180e0c62f5.png align="center")

Configure the background color

```css
#app/javascript/stylesheets/application.scss
body { background-color: lightseagreen; }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677894233194/160a1dcb-9288-456d-93f7-3710768e0656.png align="center")

Now, go to your app. You view page should have a light green background color.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677894297514/06a8190a-2b3a-481e-ba9e-85899ba4fbbf.png align="center")

---

#### **12 - Celebrate**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif align="left")

---

### **Conclusion**

That's all for today. I hope this article helped you.

Let me know if you need any additional help.