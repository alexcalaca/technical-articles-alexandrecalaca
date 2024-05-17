---
title: "ActionController::InvalidAuthenticityToken"
datePublished: Sun May 14 2023 03:05:48 GMT+0000 (Coordinated Universal Time)
cuid: clhmu3e4m000008mkhkvght0g
slug: action-controller-invalid-authenticity-token
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/gySMaocSdqs/upload/5c879157bff52b55a9d1bcedbe1ef5a3.jpeg
tags: ruby, web-development, ruby-on-rails, hashnode, 2articles1week

---

---

## Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. I'm so excited that you landed here. Hope you enjoy this new article.

By the way, I would be glad to receive your feedback about it.

Since you're already here, consider follow me on [github](https://github.com/alexcalaca) and here on [Hashnode](https://blog.alexandrecalaca.com/).

You might be interested in checking my complete [list of articles](https://blog.alexandrecalaca.com/all-articles).

---

## Objective

Throughout this article, we will explore the underlying concepts that contribute to the solution to the ActionController::InvalidAuthenticityToken error.

By understanding authenticity tokens, user sessions, form structures, and the potential threats of Cross-Site Request Forgery (CSRF) attacks, you gain insights into the root causes of this error and the measures required to mitigate it.

---

## Introduction

In the dynamic world of web development, ensuring the security and integrity of our applications is paramount. This article aims to equip you with the understanding and practical solutions needed to effectively address this error, safeguard your web applications, and provide a seamless user experience.

Let's dive in.

---

## Understand the error

The error we're going to talk about is the following

```ruby
ActionController::InvalidAuthenticityToken
```

In the Rails console, the error would look like the following

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684003711282/bf3aa6a3-92c7-4c55-a306-80f8e147f5b5.png align="center")

In your view page, this is the image you would see.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684003736649/2868686e-39c7-4486-ad58-1f94f14061c6.png align="center")


---

### The moment it happens (When)

The error `ActionController::InvalidAuthenticityToken` in a Rails application typically occurs when a form submission is rejected due to an invalid or missing authenticity token.

When a form is submitted in Rails, the authenticity token is expected to be included in the request parameters. If the token is missing or incorrect, Rails raises the `ActionController::InvalidAuthenticityToken` error as a security measure.

---

### Reason (Why)

Ruby on Rails, being a powerful web framework, incorporates several security measures, including the usage of authenticity tokens to protect against cross-site request forgery (CSRF) attacks.

Rails knows the nature of CSRF attacks and how they pose a threat to the integrity and security of web applications, it understands the mechanics of CSRF attacks, where malicious entities exploit the trust between a user's browser and a targeted application to perform unauthorized actions on behalf of the user.

So, it's not uncommon for Rails developers to encounter the dreaded `ActionController::InvalidAuthenticityToken` error, which can hinder form submissions and cause confusion.

---

### Cross-Site Request Forgery

Cross-Site Request Forgery (CSRF) attacks are a type of security vulnerability that can affect web applications, including those built with Ruby on Rails. A CSRF attack occurs when an attacker tricks a victim into unknowingly performing an undesired action on a website or application where the victim is authenticated.

In the context of Rails apps, CSRF attacks typically involve an attacker crafting a malicious request that they then force the victim's browser to execute. The attack takes advantage of the fact that web browsers automatically include cookies and other authentication information with each request made to a specific domain.

---

![white cat sitting on brown couch](https://images.unsplash.com/photo-1518288774672-b94e808873ff?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1000&q=80 align="left")

---

### Authenticity token

The authenticity token is a security measure implemented by Rails to protect against cross-site request forgery (CSRF) attacks. It is a unique token generated for each session and included in forms to verify that the form submission originated from the same application and user.

The authenticity token works as a defense mechanism to ensure that the form data originates from the same application and user who initiated the request. When a user visits a Rails application and submits a form, the authenticity token is included as a hidden field in the form or as a request header, depending on the configuration.

Rails generates a new authenticity token for each user session, making it unique and tied to that specific session. This ensures that even if an attacker manages to obtain a token, it would only be valid for that particular session and cannot be used to forge requests in other sessions.

---

### User sessions

When a user visits a Rails application, a session is created to track their interactions and maintain their state across multiple requests. The session is typically stored as a unique identifier (session ID) in a cookie or passed through other means, such as the URL or request headers.

When a form is rendered in a Rails application, the authenticity token is included as a hidden field within the form. This allows the token to be automatically submitted along with other form data when the user submits the form.

It's worth noting that the authenticity token is regenerated for each new session or user login, ensuring that even if an attacker manages to obtain a token from a previous session, it would be invalid and unusable for subsequent sessions or different users.

---

### Form submission

During the form submission, Rails checks the authenticity token to verify that it matches the expected value for the session. If the token is missing or doesn't match, Rails raises the ActionController::InvalidAuthenticityToken error, preventing the form from being processed. This mechanism helps prevent attackers from forging malicious requests by tricking users into submitting forms unknowingly.

By including the authenticity token in forms, Rails adds an extra layer of security to protect against CSRF attacks. These attacks involve an attacker tricking a user's browser into making a request on their behalf, potentially leading to unauthorized actions being performed on the user's behalf.

---

## Solution

### 1\. Rails forms

Verify possible typos in Rails forms.

Ensure that your forms include the authenticity token by using the Rails form helpers (form\_with, form\_tag, etc.). These helpers automatically generate the authenticity token and include it in the form.

---

### 2\. Application layout view page

Make sure you have the following code line right after the `title` tag:

```ruby
<%= csrf_meta_tags %>
```

---

### 3\. Protect from forgery

In your controller that’s generating the error, or in your application\_controller.rb, include the following command:

```ruby
protect_from_forgery with: :null_session
```

or

```ruby
protect_from_forgery
```

The protect\_from\_forgery command is a method provided by Ruby on Rails to protect against Cross-Site Request Forgery (CSRF) attacks.

When you call protect\_from\_forgery in a Rails controller, it adds a CSRF protection mechanism to that controller's actions. This mechanism generates an authenticity token and verifies it on non-GET requests (e.g., POST, PUT, DELETE) to ensure the request is not a result of a CSRF attack.

When I ran into this issue, this step was responsible to solve my problem.

---

### 4\. Skip authenticity token verification

In your controller that’s generating the error, or in application\_controller.rb, include the following command:

```ruby
skip_before_action :verify_authenticity_token
```

The `skip_before_action :verify_authenticity_token` command is used in Ruby on Rails to exclude a specific controller or controller action from the default CSRF (Cross-Site Request Forgery) protection provided by Rails.

By default, Rails includes the verify\_authenticity\_token method as a before\_action in controllers to automatically check the authenticity token on non-GET requests. This helps protect against CSRF attacks by ensuring that the request originated from the same application and user session.

So, pay attention if you really want to use this approach.

---

### 5\. Test it

By testing with your view page, check if you get the error message again. 

Another option is to check in your console.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684030866315/c8829b59-5da2-43a4-a98e-6f13d5757aea.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684003875990/fb02204d-9f72-4dfa-9710-6c6c69fb340b.png align="center")

---

## Conclusion

In conclusion, understanding and effectively addressing the ActionController::InvalidAuthenticityToken error in Rails is crucial for maintaining the security and integrity of your web applications. By grasping the underlying concepts of authenticity tokens, user sessions, and CSRF attacks, you can implement the necessary safeguards to protect your application and its users from malicious activities.

Throughout this article, we explored the reasons behind the occurrence of the error and provided practical solutions to resolve it. By following the recommended steps, such as verifying form structures, including authenticity tokens, and properly configuring CSRF protection, you can ensure that your Rails applications are fortified against CSRF attacks and provide a seamless user experience.

Remember, security should always be a top priority in web development, and by equipping yourself with the knowledge and tools to handle the ActionController::InvalidAuthenticityToken error, you are taking an important step towards creating robust and secure Rails applications. Keep learning, stay vigilant, and continue building with confidence.

---

## Celebrate

Way to go, guys. You did a great job. You can definitely celebrate!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

## Final thoughts

That's all for today. Thanks for reading this article.

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---