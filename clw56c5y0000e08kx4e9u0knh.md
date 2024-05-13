---
title: "How to generate a rails app with Postgresql as the database?"
datePublished: Mon May 13 2024 16:24:16 GMT+0000 (Coordinated Universal Time)
cuid: clw56c5y0000e08kx4e9u0knh
slug: how-to-generate-a-rails-app-with-postgresql-as-the-database
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/S5jD0E8DOC0/upload/b36e9f3d5ab2c44f934e340c3b4ae1fc.jpeg
tags: postgresql, ruby, ruby-on-rails, alexandrecalaca

---

---

## Make sure you have Ruby

```ruby
ruby -v
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709693658328/127e99c2-7e62-4594-bd0e-ee6b861c2180.png align="center")

---

## Make sure you have Rails

```ruby
rails -v
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709693658328/127e99c2-7e62-4594-bd0e-ee6b861c2180.png align="center")

---

## Make sure you have Postgresql

```ruby
psql --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709693658328/127e99c2-7e62-4594-bd0e-ee6b861c2180.png align="center")

---

## Generate the app

```ruby
rails _6.1.4_ new app_name -d postgresql
```

---

## Check your database.yml file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709695492707/737d3eeb-0c42-4afc-aad2-844e54a9cc18.png align="center")

---

## Perform database commands

```ruby
rails db:create
rails db:migrate
```

---

## Confirm database creation

```ruby
psql -U postgres -h localhost -d youdemee_development
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709695589451/5506c760-4264-4723-99ea-36226bc8158f.png align="center")

`youdemee_development` is the database name.

---

## **Done**

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### Reach me out

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**H**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ashnode**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---