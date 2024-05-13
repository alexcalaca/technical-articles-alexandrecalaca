---
title: "how to install yarn for a Ruby on Rails application?"
datePublished: Mon May 13 2024 16:26:26 GMT+0000 (Coordinated Universal Time)
cuid: clw56exsa001q08m7hk1hhuyy
slug: how-to-install-yarn-for-a-ruby-on-rails-application
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/06ZTGDcAQFs/upload/59e8fa1c6a5583aa4ea7c4fbdfc6e541.jpeg
tags: ruby-on-rails, yarn, alexandrecalaca

---

---

## Open a terminal

---

## Insert the keys

```ruby
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

---

## Update the repository

```ruby
sudo apt update
```

---

## Install yarn

```ruby
sudo apt install yarn
```

---

## Check installation

```ruby
yarn --version
which yarn
yarn --help
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709696065075/77ed0f6b-59fb-4b40-8cf7-92ee65caab7e.png align="center")

---

## Webpacker installation

```ruby
 rails webpacker:install
```

---

## **Done**

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me ou**[**t**](https://github.com/alexcalaca)

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