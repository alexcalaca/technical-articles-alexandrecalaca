---
title: "Setting Up RVM on Deepin Linux OS 20.9: A Step-by-Step Guide"
datePublished: Fri Nov 03 2023 19:57:40 GMT+0000 (Coordinated Universal Time)
cuid: cloj1f18t000c08jqgi539flw
slug: setting-up-rvm-on-deepin-linux-os-209-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699041094069/c0cb598b-115e-4387-8462-386b49d46a8b.png
tags: tutorial, ubuntu, linux, ruby, deepin

---

---

## RVM

RVM stands for "Ruby Version Manager." It is a tool commonly used in the Ruby and Ruby on Rails development communities to manage multiple Ruby environments and gemsets on a single system.

RVM allows developers to install and switch between different versions of Ruby, create isolated gem sets for individual projects, and manage dependencies more effectively.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## **Check your OS (optional)**

This step is just to make sure you have **Deepin Linux installed.**

```plaintext
lsb_release -a
hostnamectl
cat /etc/os-release
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772856976/3bf1885b-0024-4886-a8b3-d6a891175205.png?auto=compress,format&format=webp align="left")

---

## Update your system

Open the terminal and run the following command:

```plaintext
sudo apt update
```

---

## Install the required dependencies

```plaintext
sudo apt install apt-transport-https ca-certificates gnupg2 curl -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699040329955/6e617342-f55d-4735-a5d4-badc1656c127.png align="center")

---

## Import GPG Key

GPG stands for Gnu Privacy Guard and it is supported by the Internet Engineering Task Force ([IETF](https://www.ietf.org/)) through the [RFC 4880](https://www.ietf.org/rfc/rfc4880.txt).

The IETF publishes RFCs authored by network operators, engineers, and computer scientists to document methods, behaviors, research, or innovations applicable to the Internet.

GnuPG (more commonly known as GPG) is an implementation of a standard known as PGP (Pretty Good Privacy). It uses a system of "public" and "private" keys for the encryption and signing of messages or data.

```plaintext
curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699040381497/f63a059c-c6bb-4abc-a773-b18007660d31.png align="center")

---

## Install the RVM stable version

```plaintext
curl -sSL https://get.rvm.io | bash -s stable --ruby
```

By now, you should be able to see something like this:

![Screenshot_select-area_20221207231910.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670466689550/hvlEa0DXD.png align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699040728580/7806c7e5-97d0-4245-a5f7-48453bf2c964.png align="center")

---

## Start using RVM

```plaintext
source /home/elitebughunter/.rvm/scripts/rvm
```

---

### Check RVM installation

```plaintext
rvm -v
which rvm
```

You should be able to see something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699040797009/ee7d0d1c-b198-4402-9fb3-0e6423bf494c.png align="center")

---

## List all Ruby versions available

```plaintext
rvm list known
```

You should be able to see something like this:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670467136561/oePiQQOwU.png align="left")

---

## Celebrate

![Happy Season 2 GIF by The Office - Find & Share on GIPHY](https://media2.giphy.com/media/jQediRqu0oLXNdjDbN/giphy.gif?cid=6c09b952sfrdnl666a3hp1aeryp278rp59g3w8aj33myfbux&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g align="left")

---

### **Final thoughts**

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---