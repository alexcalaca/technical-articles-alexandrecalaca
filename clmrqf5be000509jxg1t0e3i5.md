---
title: "How to install Slack on Linux Mint 21 vanessa"
datePublished: Wed Sep 20 2023 12:40:20 GMT+0000 (Coordinated Universal Time)
cuid: clmrqf5be000509jxg1t0e3i5
slug: how-to-install-slack-on-linux-mint-21-vanessa
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695213564244/7044a800-2559-4d55-a9fd-c67c38c1bc35.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1695213607803/db43e0aa-126e-49f6-80ab-5e4d82c1ebdd.png
tags: tutorial, ubuntu, linux, slack

---

---

## Slack

Slack is a cloud-based collaboration platform and messaging app designed for teams and workplaces.

It was created as a tool to improve communication and collaboration among team members, both within organizations and for remote or distributed teams.

Slack offers a wide range of features that help teams streamline their work and communication.

---

![Suits-2x08 GIFs - Get the best GIF on GIPHY](https://media0.giphy.com/media/3o85xp2sR7StloVo9q/giphy.gif align="center")

---

## Update the repository info

In your browser, go to the following link:

```plaintext
sudo apt update
```

---

## Visit the download page

```plaintext
https://slack.com/downloads/linux
```

---

## Download the .deb file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694662636809/ffc64a41-d238-47dd-b985-955020fe8ef3.png align="center")

---

## Install

```plaintext
sudo dpkg -i Downloads/slack-desktop-4.33.90-amd64.deb
```

The `dpkg` command is a Debian Package Manager, a command-line tool used for working with Debian packages.

Debian packages are a common format for distributing software on Debian-based Linux distributions, such as Ubuntu and Linux Mint.

The `-i` flag specifies that you want to install a package.

So, when you run this command, it installs the Slack desktop application on your Linux system by processing the specified Debian package.

---

## Check slack's installation

### Through its executable file location

```plaintext
which slack
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694662877814/a7665209-3240-4727-8b32-376913f21e9e.png align="center")

---

### Through its version

```plaintext
slack -v
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694662917241/eedd4ff8-ee0a-4764-83fd-8b028d12320e.png align="center")

---

### Through its post-installation run

```plaintext
slack
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694662969881/f758b986-15a8-4a1a-be49-31b8733f325f.png align="center")

---

## Done

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

---