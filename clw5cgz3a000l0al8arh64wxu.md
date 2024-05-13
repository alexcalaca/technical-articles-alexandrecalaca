---
title: "Rails app is searching for stylesheets in the app/assets/stylesheets directory instead of app/javascript/stylesheets"
datePublished: Mon May 13 2024 19:15:59 GMT+0000 (Coordinated Universal Time)
cuid: clw5cgz3a000l0al8arh64wxu
slug: rails-app-is-searching-for-stylesheets-in-the-appassetsstylesheets-directory-instead-of-appjavascriptstylesheets
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/aG8iIT9_iqM/upload/ae95e0740fc41bb509f8b81ff1f59d5e.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## [**Situation**](https://blog.alexandrecalaca.com/rails-app-is-searching-for-stylesheets-in-the-appassetsstylesheets-directory-instead-of-appjavascriptstylesheets)

When Rails app is running, it incorrectly searches for stylesheets in the `app/assets/stylesheets` instead of the intended `app/javascript/stylesheets`, resulting in issues with the correct functioning of the stylesheets.

---

## Current configuration

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694027907551/88a415d9-4c69-4d36-a221-98527444b888.png?auto=compress,format&format=webp align="left")

---

## Brief explanation

This situation is likely due to the default asset pipeline configuration.

In Rails 6 and later, JavaScript and stylesheets are often managed differently, with JavaScript using Webpacker and stylesheets using the asset pipeline.

However, if you want to centralize your stylesheets in the `app/javascript/stylesheets` directory and use them in your application, you must ensure the following steps.

---

## Check Webpacker installation

### Via npm

```ruby
npm list | grep webpacker
```

Output

```ruby
calaca@calaca-PC ~/var/www/edume (courses-initial-configuration)$ npm list | grep webpacker
├── @rails/webpacker@5.4.4
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694028092387/2be2a4b6-e762-4843-bc7f-cd6bc52ccaa1.png?auto=compress,format&format=webp align="left")

---

### Via bundle

```ruby
bundle list | grep webpacker
```

Output

```ruby
calaca@calaca-PC ~/var/www/edume (courses-initial-configuration)$ bundle list | grep webpacker
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
  * webpacker (5.4.4)
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694028332417/22bb441f-ffc1-45d6-8457-d8810ea9707b.png?auto=compress,format&format=webp align="left")

---

## Open the webpacker.yml file

The file is located in `config/webpacker.yml`.

---

### UPdate the source\_path

In `config/webpacker.yml`:

```ruby
# config/webpacker.yml
source_path: app/javascript
```

You file should look something like the following

```ruby
# Note: You must restart bin/webpack-dev-server for changes to take effect

default: &default
  source_path: app/javascript
  source_entry_path: packs
  public_root_path: public
  public_output_path: packs
  cache_path: tmp/cache/webpacker
  webpack_compile_output: true

  # Additional paths webpack should lookup modules
  # ['app/assets', 'engine/foo/app/assets']
  additional_paths: []

  # Reload manifest.json on all requests so we reload latest compiled packs
  cache_manifest: false

  # Extract and emit a css file
  extract_css: false

  static_assets_extensions:
    - .jpg
    - .jpeg
    - .png
    - .gif
    - .tiff
    - .ico
    - .svg
    - .eot
    - .otf
    - .ttf
    - .woff
    - .woff2

  extensions:
    - .mjs
    - .js
    - .sass
    - .scss
    - .css
    - .module.sass
    - .module.scss
    - .module.css
    - .png
    - .svg
    - .gif
    - .jpeg
    - .jpg

development:
  <<: *default
  compile: true

  # Reference: https://webpack.js.org/configuration/dev-server/
  dev_server:
    https: false
    host: localhost
    port: 3035
    public: localhost:3035
    hmr: false
    # Inline should be set to true if using HMR
    inline: true
    overlay: true
    compress: true
    disable_host_check: true
    use_local_ip: false
    quiet: false
    pretty: false
    headers:
      'Access-Control-Allow-Origin': '*'
    watch_options:
      ignored: '**/node_modules/**'


test:
  <<: *default
  compile: true

  # Compile test packs to a separate directory
  public_output_path: packs-test

production:
  <<: *default

  # Production depends on precompilation of packs prior to booting for performance.
  compile: false

  # Extract and emit a css file
  extract_css: true

  # Cache manifest.json for performance
  cache_manifest: true
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694032782124/d6ed01bc-5b7a-4b31-b48a-91d8a61a309e.png?auto=compress,format&format=webp align="left")

---

## Restart the Webpacker server

In your terminal emulator:

```ruby
./bin/webpack-dev-server
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694032861185/2125edeb-26fc-4020-b17c-7ee88b1a7212.png?auto=compress,format&format=webp align="left")

---

## Import stylesheets into application.js

In the main javascript file, which is `app/javascript/packs/application.js`, add the stylesheets:

```ruby
# app/javascript/packs/application.js
import "stylesheets/application"
import "stylesheets/courses"
```

Or with the following syntax:

```ruby
# app/javascript/packs/application.js
import "../stylesheets/application.scss"
import "../stylesheets/courses.scss"
```

It'll look something like this:

```ruby
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
import "stylesheets/courses"

import "channels"
import "@fortawesome/fontawesome-free/css/all"

Rails.start()
Turbolinks.start()
ActiveStorage.start()
```

---

## Refact

### Create an index file

In `app/javascript/stylesheets/`, create a file called `index.scss`:

```ruby
touch app/javascript/stylesheets/index.scss
```

This file will serve as an entry point for your SCSS imports.

---

### Include all imports

In `app/javascript/stylesheets/index.scss`:

```ruby
@import 'application';
@import 'courses';
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694033942776/7b58a4aa-272b-4bc8-a6ce-3a83031df9cd.png?auto=compress,format&format=webp align="left")

---

### Add index to the javascript entry point file

In your JavaScript entry point file, which is `app/javascript/packs/application.js`, import the `index.scss` file:

```ruby
# app/javascript/packs/application.js
import 'stylesheets/index.scss';
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694034079278/f4414ab9-50cf-4bc8-876d-02f7c627013c.png?auto=compress,format&format=webp align="left")

---

## Check the result

### Rails server

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694034195402/61e1e30a-40d5-4e33-8ac3-61152bb64551.png?auto=compress,format&format=webp align="left")

---

### View page

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694034211475/7c9291d4-94a7-4743-87ab-5684e5c07481.png?auto=compress,format&format=webp align="left")

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