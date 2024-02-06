---
title: "How to install and configure Redis server on Pop!_OS: A step-by-step guide"
datePublished: Sun Jan 21 2024 17:45:11 GMT+0000 (Coordinated Universal Time)
cuid: clrnsgy94000809l44v7s4oip
slug: how-to-install-and-configure-redis-server-on-popos-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705859014947/0e94f647-5169-4957-a1cf-42d71c543400.png
tags: ubuntu, ruby, redis, ruby-on-rails, popos, alexandrecalaca

---

---

## Redis

Redis, which stands for Remote Dictionary Server, is an open-source, in-memory data structure store. It is often referred to as a data structure server because it supports a variety of data structures such as strings, hashes, lists, sets, and more. Redis is designed to be fast and efficient, providing high-performance data storage and retrieval.

---

## **Let's get down to business**

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="left")

---

### **Check your OS (optional)**

This step is just to make sure you have `Pop!_OS` installed.

```javascript
uname -a
hostnamectl
lsb_release -a
cat /etc/os-release
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Prerequisites

```javascript
sudo apt install lsb-release curl gpg
```

---

## Download the Redis GPG key

```javascript
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705857891256/294c2485-3da0-471f-8828-6e28fa9d3d18.png align="center")

This command downloads the Redis GPG key from the specified URL using `curl`, and then it uses `gpg` to dearmor the key and save it to the specified location with superuser privileges.

This GPG key is likely used for verifying the authenticity of the Redis packages when they are later installed or updated on the system.

---

## Create a new repository

```javascript
echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705858045788/28539c92-8011-44e4-984e-e799bbcacd60.png align="center")

this command creates a new APT repository source file (`/etc/apt/sources.list.d/redis.list`) with the Redis repository information. The repository is configured to use a GPG key for package verification, and the URL includes the distribution codename dynamically obtained from the `lsb_release -cs` command. This new source entry allows the system to fetch and install Redis packages from the specified repository.

---

## Update the local package index

```javascript
sudo apt-get update
```

Running `apt-get update` is typically the first step before installing or upgrading packages on a system. It ensures that the local package index is up-to-date, allowing you to install the latest versions of packages or check for updates to existing packages.

---

## Install Redis

```javascript
sudo apt-get install redis -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705858221748/2c8003d0-559e-49ba-a2a3-1db779b118b9.png align="center")

When you run `sudo apt-get install redis -y`, the system will download and install the Redis server package along with any necessary dependencies.

---

## Check installation

```javascript
redis-server -v
which redis-server
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705858510362/051791d2-1f2b-4cf2-a3a7-9d359ca490b0.png align="center")

### which

* This command is used to determine the path to the executable binary for the Redis server.
    
* It prints the full path to the Redis server executable, helping you identify where the Redis server binary is located in your system.
    

### version

* This command is used to check the version of the Redis server that is installed on your system.
    

---

## Status of Redis server service

```javascript
sudo systemctl status redis-server
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705858790168/33c26398-474f-480c-b3f9-7942f904874a.png align="center")

The output will provide information about whether the Redis server is active, the current process ID (PID), recent logs, and more. It's a way to check if the Redis service is running and to get details about its current state.

The `sudo systemctl status redis-server` command provides information about the status of the Redis server service, including whether it is active and details about its current state.

---

## Check if server is responsive

```javascript
redis-cli ping
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705858790168/33c26398-474f-480c-b3f9-7942f904874a.png align="center")

`ping` is a simple command that can be used to check if the Redis server is reachable and responsive. If the server is responsive, it will return "PONG."

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
