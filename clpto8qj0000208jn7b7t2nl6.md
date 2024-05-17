---
title: "Installing Telegram via default APT repository on Pop!_OS"
datePublished: Wed Dec 06 2023 11:14:01 GMT+0000 (Coordinated Universal Time)
cuid: clpto8qj0000208jn7b7t2nl6
slug: installing-telegram-via-default-apt-repository-on-popos
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/_rqDHdrKIJs/upload/648eab7ffe7da6394e0439db6e3cf45f.jpeg
tags: tutorial, linux-for-beginners, popos, alexandrecalaca

---

---

## Telegram

![Telegram Premium é lançado e custará até R$ 24,90 ao mês](https://static.poder360.com.br/2022/03/telegram-aplicativo-vpn-848x477.jpg align="left")

Telegram is a cloud-based instant messaging app that allows users to send text messages, voice messages, multimedia files, and make voice and video calls over the internet.

It was developed by Pavel Durov and his team and was first launched in 2013.

Telegram is available as a mobile app for smartphones and tablets, as well as a desktop application for Windows, macOS, and Linux.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

## **Check your OS (optional)**

This step is just to make sure you have **Pop!\_OS Linux installed.**

```basic
lsb_release -a
hostnamectl
cat /etc/os-release
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701860734378/6b1aed35-1d5c-457e-b391-ca4cb3fca87f.png align="center")

---

## Update the package manager repository

```plaintext
sudo apt update
```

---

## Install Telegram

```plaintext
sudo apt install telegram-desktop
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701860876202/8d036a2e-a88d-4573-bbbc-013902304356.png align="center")

---

## Check installation

### Executable file's path

```plaintext
which telegram-desktop
```

You should be able to see something like the following:

---

### Version

```plaintext
telegram-desktop --version
```

You should be able to see something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701861117304/31ee48de-a705-4675-8a96-9e85cbab2b10.png align="center")

---

## Done

Well-done. You did a great job.

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

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---