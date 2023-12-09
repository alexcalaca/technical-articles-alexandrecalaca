---
title: "How to install Terminator on Linux Mint 21 vanessa or any other Ubuntu-based Linux distribution?"
datePublished: Mon Sep 25 2023 21:00:31 GMT+0000 (Coordinated Universal Time)
cuid: clmzdhmwj000909md2vevc8b4
slug: how-to-install-terminator-on-linux-mint-21-vanessa-or-any-other-ubuntu-based-linux-distribution
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695675420137/7cf724fe-6ab8-47b1-bfbe-7b3c9afbeb45.png
tags: tutorial, ubuntu, linux, terminal, installation, alexandrecalaca

---

`Revisited and updated on December 09th, 2023`

---

## Terminator

Terminator is a popular choice among Linux users, particularly those who work extensively with the command line, because of its advanced features and flexibility.

It's available in the software repositories of many Linux distributions and can be installed using package managers like APT (for Debian/Ubuntu-based systems) or YUM (for Red Hat/Fedora-based systems).

---

## Let's get down to business

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="center")

---

### Check your OS

This step is just to make sure you have **Linux Mint** or a \*\*Ubuntu-\*\*based Linux distribution.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695496363425/6f056578-4c7a-4b87-929d-106b8c01f28a.png align="center")

---

## Update package manager repository

```ruby
sudo apt-get update
```

---

## Install

```ruby
sudo apt install terminator
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702148614294/afb92ec9-04eb-4777-8264-ebd25f67afc3.png align="center")

---

## Check installation

### Version

```ruby
terminator --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695675247895/87b3fbe6-610b-47a2-8655-4969f8643fd5.png align="center")

---

### Executable file's path

```ruby
which terminator
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695675242595/69d976cc-95ae-4824-a10f-2c0258878a8b.png align="center")

---

### Run

```ruby
terminator
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695675254255/930c1b49-8fec-4c6e-8703-9c9086d13bfe.png align="center")

---

## Done

---

## Celebrate

![Happy Season 2 GIF by The Office - Find & Share on GIPHY](https://media2.giphy.com/media/jQediRqu0oLXNdjDbN/giphy.gif?cid=6c09b952sfrdnl666a3hp1aeryp278rp59g3w8aj33myfbux&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g align="left")

---

## **Let's become friends**

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