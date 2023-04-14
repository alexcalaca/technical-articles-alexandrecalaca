---
title: "Rails: How do Sessions work in Rails?"
datePublished: Fri Apr 14 2023 03:13:07 GMT+0000 (Coordinated Universal Time)
cuid: clgfz58m6000009l8fjskd07i
slug: rails-how-do-sessions-work-in-rails
tags: programming-blogs, http, ruby, rails

---

Hey guys

Today, we're going to learn how Sessions work in Ruby on Rails. This article is the first part of a series called "Sessions".

This article covers the theory part about `Sessions` in Rails.

### Introduction

In recent years, web applications have grown in complexity due to the increasing need for advanced online services with rich features. Thanks to modern web technologies, developers are now capable of creating dynamic, interactive applications that can seamlessly run on various devices.

In a lot of applications, it's necessary to create ways to store data between layers (controllers and views).

### Sessions

#### Definition

A session is just a way to store data between requests.

#### Importance

Sessions are a critical component of web applications as they allow for the storage and retrieval of user-specific information across multiple requests. The following are key reasons of why sessions are so important:

1. Maintaining user state: Sessions enable web applications to remember user-specific information, such as login credentials, preferences, and shopping cart items, even if the user navigates away from the site and comes back later. This helps to provide a seamless and personalized user experience.
    
2. Security: Sessions provide a mechanism for securely managing user authentication and authorization, by ensuring that user credentials are validated for each request.
    
3. Performance: Sessions can be used to optimize the performance of web applications by reducing the number of requests to the server, as user information is stored on the server-side and can be accessed by subsequent requests.
    
4. Analytics: Sessions can be used to track user behavior and generate valuable insights about how users interact with a web application. This information can be used to improve the user experience and optimize the application's performance.
    

---

#### How do `Sessions`work?

When a user visits a Rails application, a unique session is created for that user. This session can be used to store data such as user information, shopping cart items, and more.

When a user logs into a Rails application, the application can create a new session for the user. This session is assigned a unique session ID, which is stored in a cookie on the user's computer. Each subsequent request from the user includes the session ID, allowing the server to retrieve the session data.

![criança em azul e branco camisa de manga comprida e azul jeans dungaree em cesta tecida marrom](https://images.unsplash.com/photo-1616725104776-72fd9a51dfbd?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1000&q=80 align="left")

'

#### Where are `Sessions` stored?

In Ruby on Rails, sessions are stored by default in cookies. Specifically, session data is stored in an encrypted cookie called `_session_id`. This cookie is sent back and forth between the browser and the server on each request and response, allowing the server to maintain state between requests.

Rails also supports using other storage mechanisms for sessions, such as server-side databases or external services like Redis or Memcached. To use a different storage mechanism, you would need to configure your Rails application to use the desired mechanism.

---

#### Rails Sessions and Cookies

A cookie is typically set by the Rails server in response to a request that requires session data to be stored. As an example, let's think about a Rails application that allows users to add items to a shopping cart.

When a user adds an item to their cart, the Rails server needs to store information about the item in one specific place, which is the user's session, so that it can be used later when the user decides to check out.

```apache
Set-Cookie: sessionid=BAh7B0kiD3Nlc3Npb25faWQGOgZFVEkiJTY2OTk3ZTQ3ZTdjN2IzYzA0YjYzYmY1NTVmYzVlYmEwBjsAVEkiEF9jc3JmX3Rva2VuBjsARkkiMVRmNGZZVXNITlB6Uk50MUZpd0phZ1NQTVhJYlN0Y0pBbHlURXpUSnZReXM9BjsARg%3D%3D--4fa2d54020f06585e9a9f465aaf5323526da5e14; path=/; HttpOnly
```

The previous code is an example of a cookie.

---

####   
Step by step \[Example\]

1. The user visits the shopping cart page `(/cart)` for the first time.
    
2. The Rails server receives the request and initializes a new session for the user, because this is the user's first request and there's no session ID yet.
    
3. The Rails server generates a new session ID and sets a cookie called `_session_id` in the response with the encrypted session ID and any initial session data.
    
4. The browser receives this Rails response and stores the `_session_id` cookie.
    
5. The user adds an item to their cart and submits the form, so, there's a new request.
    
6. The browser sends a new request to the Rails server with the `_session_id` cookie included.
    
7. The Rails server receives the request and decrypts the session ID from the `_session_id` cookie.
    
8. The Rails server retrieves the session data associated with the session ID, which includes information about the item the user added to their cart.
    
9. The Rails server updates the session data with the new item information and sends a response back to the browser.
    
10. The browser receives the response, which does not include any new cookies, and displays the updated shopping cart to the user.
    

In the previous steps, the session is required to store information about the user's shopping cart. The Rails server initializes a new session when the user first visits the shopping cart page, and then updates the session data as the user adds items to their cart. The `_session_id` cookie is used to link the session data to the user's browser across multiple requests.

![gato dormindo na cama](https://images.unsplash.com/photo-1548802673-380ab8ebc7b7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1000&q=80 align="left")

---

#### Session Encryption

As we said, when a browser sends a request to a Rails server that includes a `_session_id` cookie, the Rails server reads the encrypted value of the cookie and uses its secret key to decrypt it.

This `secret_key_base` value is in the `config/secrets.yml` file and it is used as the secret key to encrypt and decrypt session data. This value is unique to each Rails application and should be kept secret, as knowledge of this key allows attackers to manipulate session data.

```apache
# config/secrets.yml
development:
  secret_key_base: a387a9f65a8de8d96d47c54f902d841cbfc5b5fc5f5d3d5dd5f6dc07a12e41743db3c2a644d64c3f8a87edf0c7982146a1e9c75b79e1bc7f46472d0660c7dd2

test:
  secret_key_base: d0d05808e2f0c35842f4330df1b70288f4c4c7450f0e98ee4a4d8cc69172c9a480bfb79ec13769d5b5a35ca5f5d5f2a3ed5aa6e518a6a9d6a2c3e3a6de08437

production:
  secret_key_base: <%= ENV["SECRET_KEY_BASE"] %>
```

After being decrypted, the session ID value is used by the Rails server to look up the associated session data. This session data is typically stored in the database or in a cache, depending on the Rails configuration.

Once the session data is retrieved, the Rails server can read and modify any session variables that have been set, and then use the updated session data to respond to the current request.

In summary, the `_session_id` cookie is encrypted using a secret key known only to the Rails application, and the Rails server uses this key to decrypt the cookie and retrieve the associated session data.

---

### **Conclusion**

That's all for today. I hope this article `How do Sessions work in Rails? Part I` helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.