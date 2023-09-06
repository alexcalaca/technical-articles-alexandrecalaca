---
title: "How to install bootstrap 5 with Webpacker in a Ruby on Rails 6 application on Linux"
datePublished: Wed Sep 06 2023 10:50:17 GMT+0000 (Coordinated Universal Time)
cuid: clm7mbov2000008lc0l7z9q4k
slug: how-to-install-bootstrap-5-with-webpacker-in-a-ruby-on-rails-6-application-on-linux
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693997353496/e1b753f0-094e-4c9a-9e87-f41c2df75cac.png
tags: linux, bootstrap, web-development, ruby-on-rails

---

---

## Add bootstrap

```apache
yarn add bootstrap
```

Output

```apache
calaca@calaca-PC ~/var/www/edume (bootstrap-configuration)$ yarn add bootstrap
yarn add v1.22.19
[1/4] Resolving packages...
[2/4] Fetching packages...
[3/4] Linking dependencies...
warning " > bootstrap@5.3.1" has unmet peer dependency "@popperjs/core@^2.11.8".
[4/4] Building fresh packages...
success Saved lockfile.
success Saved 1 new dependency.
info Direct dependencies
└─ bootstrap@5.3.1
info All dependencies
└─ bootstrap@5.3.1
Done in 1.63s.
```

The command `yarn add bootstrap` is used to add the Bootstrap framework to your project using Yarn, which is a package manager for JavaScript and front-end dependencies.

Bootstrap is a popular open-source front-end framework that provides a collection of pre-designed HTML, CSS, and JavaScript components and styles for building responsive and visually appealing web applications.

---

### Check installation

```apache
yarn info boostrap version
```

Output

```apache
calaca@calaca-PC ~/var/www/edume (bootstrap-configuration)$ yarn info boostrap version
yarn info v1.22.19
2.0.0
Done in 0.99s.
```

---

## Add @popperjs/core

```apache
yarn add @popperjs/core
```

Output

```apache
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

The command `yarn add @popperjs/core` is used to add the Popper.js library to your project using Yarn.

Popper.js is a JavaScript library that provides positioning and alignment for pop-up elements, tooltips, and popovers.

It's commonly used in conjunction with other libraries and frameworks like Bootstrap to manage the positioning of elements that need to appear relative to other elements on a web page.

---

### Check installation

```apache
yarn info @popperjs/core version
```

Output

```apache
calaca@calaca-PC ~/var/www/edume (bootstrap-configuration)$ yarn info @popperjs/core version
yarn info v1.22.19
2.11.8
Done in 0.19s.
```

---

## Add the Webpacker gem package

```apache
yarn add @rails/webpacker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693945759361/bf20e4d6-6738-4706-894b-1a760e9268f0.png align="center")

---

### Check installation

```apache
npm list
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693945806037/835b8f2d-e3e8-4ef4-a8d4-0748fb7d7463.png align="center")

---

## Create a stylesheets directory

```apache
mkdir app/javascript/stylesheets
```

In Rails 6, there was a shift in how JavaScript and CSS assets are managed in the default application setup. This change was made to align with modern front-end development practices and the increasing popularity of JavaScript frameworks like React, Vue.js, and Angular.

In the context of Bootstrap 5 (or any modern CSS framework), the `app/javascript` directory is used for JavaScript modules and assets, while the `app/assets` directory is typically reserved for the asset pipeline, which is a legacy approach for managing assets in older versions of Rails.

This change was part of Rails' move toward using Webpacker, which is a tool for managing JavaScript, CSS, and other assets in Rails applications.

---

## Create the main stylesheet file

```apache
echo > app/javascript/stylesheets/application.scss
```

---

## Include CSS with Webpacker

Inside the main view file, which is `app/views/layouts/application.html.erb`, it's necessary to add the following line after the `javascript_pack_tag`.

```apache
# app/views/layouts/application.html.erb
<%= stylesheet_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
```

The file is going to look like the following:

```apache
<!DOCTYPE html>
<html>
  <head>
    <title>Edume</title>
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <%= csrf_meta_tags %>
    <%= csp_meta_tag %>

    <%= stylesheet_link_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
    <%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
    <%= stylesheet_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
  </head>

  <body>
    <%= yield %>
  </body>
</html>
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693943345970/4f9da1aa-bd57-4a57-b482-df6d89d03880.png align="center")

The previous command uses the `tylesheet_pack_tag`, which is a Rails helper method provided by Webpacker. It's used to include a stylesheet bundle that was defined in your Webpacker configuration. This method takes the name of the pack (or bundle) as an argument.

By convention, the main stylesheet for your application is often named `'application'`

In this case, we use `'application'` because is the name of the stylesheet pack that we want to include, but we can have other named packs for different parts of our application.

`'data-turbolinks-track': 'reload'`: This is an optional HTML attribute that's added to the `link` tag for the stylesheet. It's used in conjunction with Turbolinks, which is a JavaScript library used in Rails to speed up page transitions. The `data-turbolinks-track` attribute with a value of `'reload'` ensures that the stylesheet is reloaded when navigating between pages using Turbolinks.

---

## Import libraries

Inside the main javascript file, which is `app/javascript/packs/application.js`, add the following libraries:

```apache
# app/javascript/packs/application.js
import 'bootstrap/dist/js/bootstrap'
import 'bootstrap/dist/css/bootstrap'
import 'stylesheets/application'
```

The `app/javascript/packs/application.js`file would look like this:

```apache
// This file is automatically compiled by Webpack, along with any other files
// present in this directory. You're encouraged to place your actual application logic in
// a relevant structure within app/javascript and only use these pack files to reference
// that code so it'll be compiled.

import Rails from "@rails/ujs"
import Turbolinks from "turbolinks"
import * as ActiveStorage from "@rails/activestorage"
import "channels"

import 'bootstrap/dist/js/bootstrap'
import 'bootstrap/dist/css/bootstrap'
import 'stylesheets/application'

Rails.start()
Turbolinks.start()
ActiveStorage.start()
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693943792372/193fe58d-b162-4d2a-bed7-2a696b777788.png align="center")

---

## Let's test it

All the following steps are going to be performed in order to test Boostrap, webpacker and Rails 6.

---

### Configure a sample background color

Inside the `app/javascript/stylesheets/application.scss` file, add the following background color:

```apache
# app/javascript/stylesheets/application.scss
body { background-color: green; }
```

It'll look something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693944243411/ded3cfd6-2480-486e-a08f-f554821d5077.png align="center")

---

## Stop the server

In order to stop the `Rails Server`, let's press the following command:

```apache
CTRL + C
```

---

## Restart the server

```apache
rails server
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693944348977/dc8117f5-2935-45e9-a2a0-ec4ca2d1e5a5.png align="center")

---

## Access a specific page

---

### Possible issues

Skip these if you don't run accross any issue.

### Cannot find package '@babel/plugin-proposal-private-methods'

```apache
node:internal/process/promises:279
            triggerUncaughtException(err, true /* fromPromise */);
            ^

Error: Cannot find package '@babel/plugin-proposal-private-methods' imported from /home/calaca/var/www/edume/babel-virtual-resolve-base.js
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693946187724/d970e7ea-15a3-44eb-8671-f34b62230cb0.png align="center")

Solution

```apache
yarn add @babel/plugin-proposal-private-methods
npm install @babel/plugin-proposal-private-methods
```

---

### @babel/plugin-proposal-private-property-in-object version is not meant to be imported

```apache
Error: [BABEL]: --- PLACEHOLDER PACKAGE ---
This @babel/plugin-proposal-private-property-in-object version is not meant to
be imported. Something is importing
@babel/plugin-proposal-private-property-in-object without declaring it in its
dependencies (or devDependencies) in the package.json file.
Add "@babel/plugin-proposal-private-property-in-object" to your devDependencies
to work around this error. This will make this message go away.
 (While processing: /home/calaca/var/www/edume/node_modules/@babel/plugin-proposal-private-property-in-object/lib/index.js)
    at Object.<anonymous> (/home/calaca/var/www/edume/node_modules/@babel/plugin-proposal-private-property-in-object/lib/index.js:28:7)
    at Module._compile (/home/calaca/var/www/edume/node_modules/v8-compile-cache/v8-compile-cache.js:192:30)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1159:10)
    at Module.load (node:internal/modules/cjs/loader:981:32)
    at Function.Module._load (node:internal/modules/cjs/loader:822:12)
    at Module.require (node:internal/modules/cjs/loader:1005:19)
    at require (/home/calaca/var/www/edume/node_modules/v8-compile-cache/v8-compile-cache.js:159:20)
    at loadPartialConfigAsync (/home/calaca/var/www/edume/node_modules/@babel/core/lib/config/index.js:34:85)
    at Object.<anonymous> (/home/calaca/var/www/edume/node_modules/babel-loader/lib/index.js:126:26)
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693946561394/a99a9d33-199b-474a-b488-d9b1ffafccb0.png align="center")

Solution

```apache
npm install --save-dev @babel/plugin-proposal-private-property-in-object
```

---

## Test it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693947546363/58796939-644c-4769-a3ec-47cd43612e23.png align="center")

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

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---