---
title: "Step-by-step guide: Setting up Rspec in your existing rails 7 project for effective testing"
datePublished: Mon May 13 2024 19:03:56 GMT+0000 (Coordinated Universal Time)
cuid: clw5c1htm001309l1htdmauti
slug: step-by-step-guide-setting-up-rspec-in-your-existing-rails-7-project-for-effective-testing
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715626948813/b10314f3-8740-4889-a724-f42399cfcdd3.png
tags: ruby, ruby-on-rails, testing, alexandrecalaca

---

---

## Rspec

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707702769765/de15d96f-6643-421e-962f-de483cca9515.png align="center")

`RSpec` is a testing framework for the Ruby programming language, and it is commonly used in the context of Ruby on Rails applications.

RSpec is designed to support Behavior-Driven Development (BDD) and provides a domain-specific language (DSL) for writing expressive and readable tests.

---

If you want to follow along, just check [this branch](https://github.com/alexcalaca/query-objects-rails/tree/rspec-setup).

---

### Add rspec to the gemfile

```javascript
group :development, :test do
  gem 'rspec-rails'
  gem "debug", platforms: %i[ mri mingw x64_mingw ]
end
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707703145402/0d846747-f3af-49a3-a8a8-0cb4004a68a3.png align="center")

---

### **Install the dependencies**

```javascript
bundle install
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707703223332/f54528f3-dc2e-49ba-98b8-067f2c2080f0.png align="center")

---

### **Check the installation**

```javascript
gem list rspec
gem list | grep rspec
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707703360779/a703fa1d-bf89-4d92-8b76-bf7cdabdc168.png align="center")

---

### Generate basic rspec configuration

```javascript
rails generate rspec:install
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707703542037/f1d6c852-034e-43c1-bf5e-7880345d1a74.png align="center")

---

### Run rspec

```javascript
bundle exec rspec
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707703817542/4b7fd610-0499-4c86-bfb7-8a9ecc1b6c7a.png align="center")

---

## **Done**

---

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="center")

---

### **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@devcenterguides)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

### **Final thoughts**

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

---