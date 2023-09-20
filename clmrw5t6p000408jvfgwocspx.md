---
title: "How to install Telegram on Linux Mint 21 vanessa or any other Ubuntu-based Linux distribution using the terminal emulator"
datePublished: Wed Sep 20 2023 15:21:02 GMT+0000 (Coordinated Universal Time)
cuid: clmrw5t6p000408jvfgwocspx
slug: how-to-install-telegram-on-linux-mint-21-vanessa-or-any-other-ubuntu-based-linux-distribution-using-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/_rqDHdrKIJs/upload/0cd944f310a955b6c995ce2fb3b7f30c.jpeg
tags: tutorial, ubuntu, linux, telegram, linux-mint

---

---

## Telegram

Telegram is a cloud-based instant messaging app and communication platform. It was created by Pavel and Nikolai Durov and was first launched in 2013.

Telegram is known for its focus on privacy, security, and speed.

---

![Suits-2x08 GIFs - Get the best GIF on GIPHY](https://media0.giphy.com/media/3o85xp2sR7StloVo9q/giphy.gif align="center")

---

## Check your OS

```ruby
lsb_release -a
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695222422291/f54778c4-2102-401a-a457-092c3cfe79f7.png align="center")

---

## Update system's package repository

```plaintext
sudo apt update
```

---

## Install Telegram

```plaintext
sudo apt install telegram-desktop -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694660852949/ef7c1aa1-b38e-4fc4-aa4f-f72c55dc8e0e.png align="center")

---

## Check installation

### Through the executable file's path

In your terminal emulator:

```plaintext
which telegram-desktop 
```

Output

```ruby
elitebughunter@elitebughunter-linux-mint:~$ which telegram-desktop 
/usr/bin/telegram-desktop
```

---

### Through its version

```ruby
telegram-desktop -v
```

---

### Through its post-installation run

```ruby
telegram-desktop
```

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