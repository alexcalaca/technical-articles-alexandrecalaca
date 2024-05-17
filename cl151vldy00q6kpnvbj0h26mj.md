---
title: "Error: RVM is not a function, selecting rubies with 'rvm use ...' will not work on Kubuntu"
datePublished: Thu Mar 24 2022 13:48:32 GMT+0000 (Coordinated Universal Time)
cuid: cl151vldy00q6kpnvbj0h26mj
slug: error-rvm-is-not-a-function-selecting-rubies-with-rvm-use-will-not-work-on-kubuntu
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1648128426440/9MxnZEVx0.png
tags: ubuntu, linux, ruby

---

Hey guys

In case you're using Kubuntu 20.04.4 and you you came across with the following error message: 

```
RVM is not a function, selecting rubies with 'rvm use ...' will not work on Kubuntu
``` 
The complete error message is this

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648127901933/y_4BBVLEO.png)

Part of our development activities is to understand error messages, basically, the message says that we need to allow login shell.

### Solution
1. Go to `settings`, `Edit current profile`
You'll end up in a window like this

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648128426440/9MxnZEVx0.png)

2. In the command field, after the text, add ` -l` 
```
/bin/bash -l
``` 
You'll get something like this


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648129234593/OX3Q8qeXh.png)

3. Restart the Kubuntu `konsole`
You won't get any error message

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648129264677/omToi4Uf5.png)

4. Celebrate lol

That's all for today.
Feel free to reach out to me if you have any questions.