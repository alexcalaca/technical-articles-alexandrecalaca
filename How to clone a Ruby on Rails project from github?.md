---
title: "How to clone a Ruby on Rails project from  github?"
datePublished: Wed Jun 07 2023 01:34:10 GMT+0000 (Coordinated Universal Time)
cuid: clil1dzvm000b09i2ckax3y57
slug: how-to-clone-a-ruby-on-rails-project-from-github
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HLQDfaJUTVI/upload/aa02c8b806839d4357f0cafdfa9b46c6.jpeg
tags: ruby, github, web-development, ruby-on-rails

---

---

### 0-Get the link

In your GitHub repo page, go to `Code`, `SSH`, then you should be able to see the link. Copy it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686101400830/553d10f1-cdb5-450c-a393-c4d8fb830948.png align="center")

---

### 1-Git clone command

```ruby
git clone git@github.com:alexcalaca/coding-challenges-ruby.git
```

Run the previous command in your desired folder.

Note that it's not necessary to create a specific folder for the project, because a new one will be created automatically.

---

### 2-Check

```ruby
ls
```

you should see a new folder with the project name.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686100507898/6f67f275-0e51-4cae-8ca7-c925c4bf7548.png align="center")

In my example, the new project is `coding-challenges-ruby`.

---

### 3-Install dependencies

```apache
bundle install
```

---

### 4-Set up database

```apache
rails db:setup
```

The `bin/rails db:setup` command will create the database, load the schema, and initialize it with the seed data.

---

### 5-Run migrations

```apache
rails db:migrate
```

Note that running the `db:migrate` command also invokes the `db:schema:dump` command, which will update your `db/schema.rb` file to match the structure of your database.

---

### 6-Start the server

```apache
rails server
```

The `bin/rails server` command launches a web server that comes bundled with Rails. You'll use this any time you want to access your application through a web browser.

---

### Be happy

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's get to know each other**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---
