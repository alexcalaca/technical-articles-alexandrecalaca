---
title: "How to generate a new rails app with a specific Rails version"
datePublished: Thu May 09 2024 00:46:37 GMT+0000 (Coordinated Universal Time)
cuid: clvyj2wvk000b0al46mhc62nh
slug: how-to-generate-a-new-rails-app-with-a-specific-rails-version
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/8B3d1ez-tRE/upload/09b5d36d9317eca81394a6a400d85686.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## Introduction

---

## Goal

My goal is to create a new app with the `5.2` Rails version.

---

## Make sure you have Ruby installed

```javascript
rbenv versions
ruby -v
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708481713489/1ec5afe4-30a1-4c20-8870-83bce60cd4da.png align="center")

---

## Check the current installed Rails versions

```javascript
gem list rails --local
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708482054318/ac28bcc4-1369-4919-8515-e72138157cd8.png align="center")

If you get nothing, it's because there's no Rails version associated with your current Ruby version.

---

## List valid Rails versions

```javascript
gem search '^rails$' --all
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708482761739/fedd2dba-3278-4337-b30a-f3d77d2787a9.png align="center")

---

## Install the desired Rails version

```javascript
gem install rails -v '5.2' -V --no-document
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708483106556/f3ac9c2e-cfb7-4b1f-9c28-cc6664658f2c.png align="center")

---

## Check the current installed Rails versions

```javascript
gem list rails --local
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708483195771/43997491-eb45-411e-9399-3eee34ae6b48.png align="center")

---

## Double check the version

```javascript
rails -v
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708483268623/6dce8368-91ee-4f60-a3f6-76f478075e5c.png align="center")

---

## Rehash the directory

```javascript
rbenv rehash
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708483363395/bfb07735-6a8d-42df-9b07-9464417ac812.png align="center")

---

## Create the app

```javascript
rails _5.2.0_ new myapp-backend --api
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708483676909/ac3acc90-9f41-4ffc-8e30-76018b097959.png align="center")

---

## Check the new app

cd app\_name

---

## **Don**[**e**](https://github.com/alexcalaca)

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me out**

* [**Gi**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**h**](https://github.com/alexcalaca)[**u**](https://hashnode.com/onboard?next=https%3A%2F%2Fdevcenterguides.com%2F)[**b**](https://github.com/alexcalaca)
    
* [**Li**](https://github.com/alexcalaca)[**n**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**k**](https://github.com/alexcalaca)[**e**](https://hashnode.com/onboard?next=https%3A%2F%2Fdevcenterguides.com%2F)[**dIn**](https://github.com/alexcalaca)
    
* [**H**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ash**](https://github.com/alexcalaca)[**n**](https://hashnode.com/onboard?next=https%3A%2F%2Fdevcenterguides.com%2F)[**o**](https://github.com/alexcalaca)[**d**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**e**](https://github.com/alexcalaca)
    
* [**Yo**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ut**](https://github.com/alexcalaca)[**u**](https://hashnode.com/onboard?next=https%3A%2F%2Fdevcenterguides.com%2F)[**b**](https://github.com/alexcalaca)[**e**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    

---

### Final thoughts

Thank you for taking the time to read our article.

If you have any questions, thoughts, suggestions, or corrections, please feel free to share them with us.

Your feedback is valuable, and we eagerly anticipate hearing from you.

Don't hesitate to suggest topics for future blog articles. Until next time!