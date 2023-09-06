---
title: "How to Install FontAwesome with Yarn and Webpacker in Rails 6?"
datePublished: Wed Sep 06 2023 11:47:51 GMT+0000 (Coordinated Universal Time)
cuid: clm7odpms001008mi6gov17dr
slug: how-to-install-fontawesome-with-yarn-and-webpacker-in-rails-6
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694000779116/f042ec1f-843a-415c-92b8-98de745006a3.png
tags: font-awesome, bootstrap, web-development, ruby-on-rails

---

---

## FontAwesome

Font Awesome is a popular collection of icons and symbols that you can use in web development to enhance the visual appeal and functionality of your website or application.

---

## Install FontAwesome via yarn

```apache
yarn add @fortawesome/fontawesome-free
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693999822556/8a45bda8-54f0-4fa8-a28a-8a1f03fb86f6.png align="center")

---

### Check installation

```apache
npm list
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693999856692/e1f20873-5733-4cde-a9cd-113c29a8711d.png align="center")

---

## Import FontAwesome

In the main javascript file, which is `app/javascript/packs/application.js`, add the following:

```apache
# app/javascript/packs/application.js
import "@fortawesome/fontawesome-free/css/all"
```

Output

```apache
# app/javascript/packs/application.js
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
import "stylesheets/application"
import "channels"
import "@fortawesome/fontawesome-free/css/all"

Rails.start()
Turbolinks.start()
ActiveStorage.start()
```

The statement import "@fortawesome/fontawesome-free/css/all" is used to import the Font Awesome icon library's CSS file, which includes all the icon styles and definitions, into your JavaScript code. This is typically done in a JavaScript or TypeScript file to ensure that the Font Awesome icons are available and styled properly when used in your web application.

---

## Restart the server

In the terminal emulator:

```apache
CTRL + C
rails start
```

---

## Add an icon

Choose any view page and insert a fontAwesome icon.

```apache
# app/views/test/index.html.erb
<h1>Test#index</h1>
<p>Find me in app/views/test/index.html.erb</p>
<i class="far fa-gem fa-spin fa-3x"></i>
Home
```

Full code:

```apache
# app/views/test/index.html.erb
<h1>Test#index</h1>
<p>Find me in app/views/test/index.html.erb</p>
<i class="far fa-gem fa-spin fa-3x"></i>
Home
```

---

## Check the result

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694000673726/f50d7818-ce38-4dfb-99a0-9825ee7ceff8.png align="center")

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