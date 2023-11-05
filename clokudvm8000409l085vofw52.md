---
title: "Telegram Installation Guide for Deepin Linux OS 20.9"
datePublished: Sun Nov 05 2023 02:16:21 GMT+0000 (Coordinated Universal Time)
cuid: clokudvm8000409l085vofw52
slug: telegram-installation-guide-for-deepin-linux-os-209
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699121798302/6177a800-8079-43c8-9c11-5457e8c3e833.jpeg
tags: tutorial, linux, linux-basics, deepin, linux-commands

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

This step is just to make sure you have **Deepin Linux installed.**

**COPY**

**COPY**

```basic
lsb_release -a
hostnamectl
cat /etc/os-release
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772856976/3bf1885b-0024-4886-a8b3-d6a891175205.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Go to the official website

Go to the [official website](https://desktop.telegram.org/) or click directly on the following link: [https://desktop.telegram.org/](https://desktop.telegram.org/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697938023897/f1176cc6-427e-4e16-bfd2-0d2439d319a4.png align="center")

---

## Download Telegram

Click on the **Get TEelegram for Linux x64** button or clicked directly on the following link: [https://telegram.org/dl/desktop/linux](https://telegram.org/dl/desktop/linux)

---

## Update the system's package repository

```plaintext
sudo apt update
```

---

## Extract the file

```plaintext
cd Downloads/
tar -xJvf tsetup.4.11.3.tar.xz 
```

Output

```plaintext
elitebughunter@elitebughunter-PC:~/Downloads$ ls
docker-desktop-4.25.0-amd64.deb  Others  tsetup.4.11.3.tar.xz
elitebughunter@elitebughunter-PC:~/Downloads$ tar -xJvf tsetup.4.11.3.tar.xz 
Telegram/
Telegram/Updater
Telegram/Telegram
elitebughunter@elitebughunter-PC:~/Downloads$ 
```

---

### Brief explanation

* `tar`: This is the command used for working with archives (Tape ARchives). In this case, you are using `tar` to extract the contents of the archive file.
    
* `-x`: This option tells `tar` to extract the files from the archive.
    
* `-J`: This option specifies that the archive is in the XZ format, a compression format similar to gzip but with better compression ratios.
    
* `-v`: This option stands for "verbose," and it makes `tar` provide detailed information about the extraction process, listing the files as they are extracted.
    
* `-f`: This option is used to specify the file to be operated on, in this case, "tsetup.4.10.3.tar.xz."
    

---

## Check extracted files

```plaintext
ls Telegram/
```

```basic
elitebughunter@elitebughunter-PC:~/Downloads$ ls Telegram/
Telegram  Updater
elitebughunter@elitebughunter-PC:~/Downloads$ pwd
/home/elitebughunter/Downloads
elitebughunter@elitebughunter-PC:~/Downloads$ ls
docker-desktop-4.25.0-amd64.deb  Others  Telegram  tsetup.4.11.3.tar.xz
elitebughunter@elitebughunter-PC:~/Downloads$ ls Telegram/
Telegram  Updater
elitebughunter@elitebughunter-PC:~/Downloads$ 
```

---

## Move Telegram binary

```basic
sudo mv Telegram/ /opt/telegram
```

Output

```basic
litebughunter@elitebughunter-PC:~/Downloads$ sudo mv Telegram/ /opt/telegram
[sudo] password for elitebughunter: 
Verification successful
```

The `/opt/telegram` is the destination directory where we want to move the "Telegram" directory. `/opt` is a common location for installing optional or third-party software on Linux systems.

This is a common method for organizing and installing software on Linux systems. After moving, the software installed in "/opt/telegram" can be run from there, and it may require administrative privileges due to the use of sudo.

---

## Create link

```plaintext
sudo ln -sf /opt/telegram/Telegram /usr/bin/telegram
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697940659757/0528308c-2592-4c43-9a70-7f16ce010865.png align="center")

The command sudo `ln -sf /opt/telegram/Telegram /usr/bin/telegram` creates a symbolic link from the `/usr/bin/telegram` location to the /opt/telegram/Telegram binary executable file.

So, when we run sudo ln -sf /opt/telegram/Telegram /usr/bin/telegram, we are creating a symbolic link named `telegram` in the `/usr/bin` directory that points to the Telegram executable in "`/opt/telegram/Telegram`."

This allows us to run the Telegram application from the command line by simply typing telegram.

---

## Check installation

### Executable file's path

```plaintext
which telegram
```

You should be able to see something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697940983391/c5a3a508-e550-4e42-813a-bbccc0d26583.png align="center")

---

## Run Telegram

```plaintext
telegram
```

You should be able to see something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697941121021/d54a7dfd-477e-4afa-9593-7f55b993da6d.png align="center")

---

## Check installation

In your terminal emulator:

```plaintext
telegram-desktop
```

---

## **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/elitebughunter)
    
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