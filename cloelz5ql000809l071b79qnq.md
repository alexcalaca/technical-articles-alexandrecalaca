---
title: "Installing Discord on Deepin Linux 20.9 via the command line"
datePublished: Tue Oct 31 2023 17:34:20 GMT+0000 (Coordinated Universal Time)
cuid: cloelz5ql000809l071b79qnq
slug: installing-discord-on-deepin-linux-209-via-the-command-line
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/sIFCJHrUWPM/upload/293b40e531e8d0e03fab33af210af139.jpeg
tags: tutorial, linux, linux-for-beginners, deepin

---

---

## Discord

Discord is a popular communication platform that primarily focuses on enabling text, voice, and video communication.

It was initially created for gamers to communicate with each other while playing online games, but it has since grown to become a widely used communication tool for various communities and purposes.

---

## Note

My articles are constantly evolving, and I welcome any feedback, corrections, or suggestions you may have. Please don't hesitate to share them with me, and I'll be grateful for your input.

Give me a shout or add me:

* [**Github**](https://github.com/elitebughunter)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Check your OS (optional)

This step is just to make sure you have **Deepin Linux installed.**

```ruby
lsb_release -a
hostnamectl
cat /etc/os-release
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772856976/3bf1885b-0024-4886-a8b3-d6a891175205.png align="center")

---

## Navigate to the official page

Go to the following link and click on `Download`

```apache
https://discord.com/download
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772991491/495d1112-083f-46ca-ae1f-94b7ee1dc9fd.png align="center")

---

## Save the deb package

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698773073388/6a758170-50e4-490c-84a1-8610e487a71c.png align="center")

---

## Install

```ruby
sudo dpkg -i ~/Downloads/discord-0.0.33.deb
```

Replace `Downloads/discord-0.0.33.deb` with your actual filename and path.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698773203089/1cc1bab5-1019-41af-8951-f73101c4bc85.png align="center")

---

### Brief explanation

The `sudo dpkg -i discord-package-name.deb` command is used to install a Debian package (with a .deb extension) on a Debian-based Linux system, such as Ubuntu or Deepin.

`dpkg` is the Debian Package Manager, a tool used to install, configure, and manage software packages on Debian-based systems.

`-i` is an option for the `dpkg` command, which specifies that you want to install a package.

---

## Run

```apache
discord
```

### Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698773564696/5161ed5c-2e05-4e26-be4b-5e6c8ba087ca.png align="center")

---

## Done

---

## **Celebrate**

![Happy Season 2 GIF by The Office - Find & Share on GIPHY](https://media2.giphy.com/media/jQediRqu0oLXNdjDbN/giphy.gif?cid=6c09b952sfrdnl666a3hp1aeryp278rp59g3w8aj33myfbux&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/elitebughunter)
    
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