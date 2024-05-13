---
title: "How to install bootstrap 5 with Webpacker in a Ruby on Rails 6 application on Linux"
datePublished: Mon May 13 2024 16:14:27 GMT+0000 (Coordinated Universal Time)
cuid: clw55zj57000209jteexo0ttg
slug: how-to-install-bootstrap-5-with-webpacker-in-a-ruby-on-rails-6-application-on-linux
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715616839186/5a6f9cac-b5c7-4188-8555-e6d2a6e96de4.png
tags: ubuntu, css, bootstrap, ruby-on-rails, popos, alexandrecalaca

---

---

## Open the terminal

---

## **Add bootstrap**

```ruby
yarn add bootstrap
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709780517712/3f4f61b4-5db6-4c57-9585-65c33d3275ef.png align="center")

The command `yarn add bootstrap` is used to add the Bootstrap framework to your project using Yarn, which is a package manager for JavaScript and front-end dependencies.

Bootstrap is a popular open-source front-end framework that provides a collection of pre-designed HTML, CSS, and JavaScript components and styles for building responsive and visually appealing web applications.

---

### **Check installation**

```ruby
yarn info boostrap version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709780586617/74d036b9-9acb-4911-b0d3-12c1522f9891.png align="center")

---

## **Add**@[@popperjs](@popperjs)

```ruby
yarn add @popperjs/core
```

Output

```ruby
yarn add v1.22.19
[1/4] Resolving packages...
[2/4] Fetching packages...
[3/4] Linking dependencies...
[4/4] Building fresh packages...
success Saved lockfile.
success Saved 1 new dependency.
info Direct dependencies
└─ @popperjs/core@2.11.8
info All dependencies
└─ @popperjs/core@2.11.8
Done in 1.62s.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709780654805/276176c9-cb09-4c03-a4fd-85662c24dca6.png align="center")

The command `y`[`rn add @`](https://hashnode.com/@popperjs)`popperjs/core` is used to add the Popper.js library to your project using Yarn.

Popper.js is [a JavaScr](https://hashnode.com/@popperjs)ipt library that provides positioning and alignment for pop-up elements, tooltips, and popovers.

It's commonly [used in](https://hashnode.com/@popperjs) conjunction with other libraries and frameworks like Bootstrap to manage the positioning of elements that need to appear relative to other elements on a web page.

---

### **Check installation**

```ruby
yarn info @popperjs/core version
```

Output

```ruby
(bootstrap-configuration)$ yarn info @popperjs/core version
yarn info v1.22.19
2.11.8
Done in 0.19s.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709780734257/156a75b8-8009-468c-a60d-ba4e3189a276.png align="center")

---

## **Add the Webpacker gem package**

```ruby
yarn add @rails/webpacker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709780837784/74ae296c-b1be-43f7-8ebf-58167c845db0.png align="center")

---

### Check installation

```ruby
npm list
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709780840268/72f34616-88ca-4a8d-8631-6db159a5d62a.png align="center")

---

## Open any view page

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709781342801/dc21431f-24ee-491a-adca-1bd6f3c93c39.png align="center")

If you pay attention, the font is different. It's due to bootstrap.

---

## Done

---

### **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### **Final thoughts**

I hope this article has been helpful to you. Please feel free to reach out if you have any questions. Your thoughts, suggestions, and corrections are more than welcome.

By the way, don't hesitate to drop your suggestions for new blog articles.

I look forward to seeing you next time