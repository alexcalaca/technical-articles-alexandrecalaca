---
title: "Google Chrome: DevTools failed to load source map: Could not load content for XXX"
datePublished: Tue Mar 28 2023 02:57:19 GMT+0000 (Coordinated Universal Time)
cuid: clfro3fwy00000al4f24y06ca
slug: google-chrome-devtools-failed-to-load-source-map-could-not-load-content-for-xxx
tags: chrome, backbonejs, deepin

---

Hey guys, how have you been?

Today, we are going to learn how to solve the following error message: `DevTools failed to load source map: Could not load content for XXX`

To be more specific, here's the complete error message:

![](https://lh4.googleusercontent.com/mL03Iv8vOHgHU_7WIZf0DuUnTKeX-LRnGGqAJgybyx6MUo0OpQx3wKgID0J-PpKnaFc8eKh6luHuZbhJE9UgEhD14YE9nrPPlGiWJMQflU9ArsY5WbRmtkXHVfTeUhZ93mIBq-MRvaH-WMv3Et-GRoY align="left")

```ruby
DevTools failed to load source map: Could not load content for XXX: System error: net::ERR_FILE_NOT_FOUND
```

### Current environment

Here's the snapshot of the app at the moment.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679969037495/fa9d8e00-6cff-4bbf-a6ed-940691792bb9.png align="center")

Here is the current `Google Chrome's` version

Path: Three vertical dots at the top right -&gt; Help -&gt; About Google Chrome

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679969184414/ecc39b38-980d-4007-ba5f-40fc3cfc5fe7.png align="center")

or via terminal

```pgsql
google-chrome --version
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679969311201/e0618b48-9dd0-4dc8-89da-9f7baac37e3f.png align="center")

My operating system is \`Deepin Os 20.7\`

```pgsql
lsb_release -a
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679969399873/c038c341-4cc8-46b8-b162-6397bbbc6aee.png align="center")

My operating system is `Deepin OS 20.7.1`, a debian-based linux distribution.

You can check yours by running the following command:

```ruby
lsb_release -a
```

---

### **Introduction**

#### What's `Chrome DevTools`?

Chrome DevTools is a set of web developer tools built directly into the Google Chrome browser.

#### When does the error happen?

It happens when we \``inspect`\` Google Chrome in order to use Chrome's `console`. run `rails server` and we try to render a view page.

Google Chrome's `inspect` functionality is available through the `CTRL + Shift + C` shortcut.

Google Chrome's `console` can be accessed directly by pressing `CTRL + Shift + J.`

---

### **Solution**

#### **1 - Open Google Chrome's developer tools**

```ruby
CTRL + Shift + I
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971830754/2bea2c51-e8f1-4063-a5e0-6a12da15cc91.png align="center")

---

#### **2 - Settings -&gt; Preferences**

You should get something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971081392/54fd92e8-df31-46cc-a2b7-909b0a9d90cc.png align="center")

---

#### **3 - Disable** `Enable Javascript source maps`

The result should be something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971400919/ba884b7d-fd3e-47a1-9429-3f1e6a30fe05.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971226217/98840339-bb99-4db5-a527-6e1dd90f7c5a.png align="center")

---

#### **4 - Disable** `Enable CSS source maps`

The result should be something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971400919/ba884b7d-fd3e-47a1-9429-3f1e6a30fe05.png align="center")

---

#### **5 - Check the result**

You'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971400919/ba884b7d-fd3e-47a1-9429-3f1e6a30fe05.png align="center")

Both values need to disabled.

---

#### **6 - Test it**

Reload the page or open Google Chrome again.

```ruby
google-chrome
```

You should be able to see something like this. So, no error messages.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679971521695/7b5550ee-31ab-49a0-a46e-32e381ccffbd.png align="center")

---

#### **7 - Celebrate**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif align="left")

---

### **Conclusion**

That's all for today. I hope this article helped you. We learned how to solve the `DevTools failed to load source map: Could not load content for XXX: System error: net::ERR_FILE_NOT_FOUND` error message.

Let me know if you need any additional help.