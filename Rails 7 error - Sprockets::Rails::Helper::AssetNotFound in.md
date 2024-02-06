---
title: "Rails 7 error - Sprockets::Rails::Helper::AssetNotFound in"
datePublished: Sun Jan 21 2024 18:46:17 GMT+0000 (Coordinated Universal Time)
cuid: clrnunizu000409jx6wa4dz38
slug: rails-7-error-sprocketsrailshelperassetnotfound-in
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705862729770/e45339bf-c337-442b-aa7b-dec00c203881.png
tags: ruby, javascript, ruby-on-rails, alexandrecalaca

---

---

## Error

### Full error

```javascript
Sprockets::Rails::Helper::AssetNotFound in Pages#home
Showing /home/elitebughunter/www/ebh/my-app Extracted source (around line #10):

/app/views/layouts/application.html.erb where line #10 raised:
The asset "application.js" is not present in the asset pipeline.

    <%= stylesheet_link_tag "application", "data-turbo-track": "reload" %>
    <%= javascript_include_tag "application", "data-turbo-track": "reload", type: "module" %>
  </head>
  <body>
```

### Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705861907717/4749550c-e529-4a00-a26a-fd4ce6562418.png align="center")

---

## Situation

In a new Rails 7 application, after running `rails server` or `./bin/dev`, it shows that view page error.

The problem seems to be in the `application.html.erb:10` file.

---

## Context

### Gemfile

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705862153819/b0432ae2-2226-4845-bc55-0b813d0e7af5.png align="center")

### Main layout file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705862227566/a7ea9f36-851b-4e70-ad2b-cf858ef24ef9.png align="center")

---

## Solution

In the `application.html.erb`:10, change from `application` to `turbo`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705862399743/8d1c4d33-6595-49b9-b8df-65ea06d27cd8.png align="center")

---

## Test it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705862426065/d092795c-16f3-450f-acdd-77674d02b628.png align="center")

---

## **Done**

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

## **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---
