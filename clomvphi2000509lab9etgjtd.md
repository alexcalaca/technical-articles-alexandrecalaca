---
title: "How to set up Telegram manually on Fedora following good Linux practices"
datePublished: Mon Nov 06 2023 12:28:55 GMT+0000 (Coordinated Universal Time)
cuid: clomvphi2000509lab9etgjtd
slug: how-to-set-up-telegram-manually-on-fedora-following-good-linux-practices
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699273584856/b53e173a-20d8-4a67-9364-fcbf64fc2c4d.jpeg
tags: linux, linux-for-beginners, linux-basics, alexandrecalaca

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

This step is just to ensure you have **Fedora 38 Linux installed. You can pick up one command or you can use them all.**

### /etc/os-release

```plaintext
cat /etc/os-release
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910445814/c08acc61-4276-4d0c-885a-27e3c1a07536.png align="center")

---

### hostnamectl

```plaintext
hostnamectl
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910683442/f37384f0-4274-498a-8130-82c4d90d01aa.png align="center")

When you run `hostnamectl` without any options, it provides detailed information about the system's hostname, operating system, kernel, and other system-related settings.

---

## lsb\_release

```plaintext
lsb_release -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910719446/6460fa24-aa93-4c5c-9101-d45a5b382fe8.png align="center")

`lsb_release` is a command-line utility commonly found in Linux distributions that adhere to the Linux Standard Base (LSB). The LSB is a standardization initiative that aims to increase compatibility between different Linux distributions by defining a common set of libraries and conventions.

---

### uname

```plaintext
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910869580/e24b0907-cf0f-4a3f-924e-021fb67670a4.png align="center")

The `uname -a` command is used to display detailed system information about the Linux operating system. It provides information about the system's kernel and other system-related details.

---

## Go to the official website

Go to the [official website](https://desktop.telegram.org/) or click directly on the following link: [https://desktop.telegram.org/](https://desktop.telegram.org/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697938023897/f1176cc6-427e-4e16-bfd2-0d2439d319a4.png align="center")

Ps: A good approach would be to download this file using `wget.`

---

## Download Telegram

Click on the **Get Telegram for Linux x64** button or click directly on the following link: [https://telegram.org/dl/desktop/linux](https://telegram.org/dl/desktop/linux)

---

## Check downloaded file

```plaintext
ls ~/Downloads/
```

Your output should include a file called something like the following:

```plaintext
[elitebughunter@192 ~]$ ls ~/Downloads/
tsetup.4.11.3.tar.xz
```

Ps: The best approach would be to use the `/tmp/` folder.

---

## Extract the file

```plaintext
tar -xJvf ~/Downloads/tsetup.4.10.3.tar.xz -C /opt/
```

Your output should be something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697939934858/3eee38de-dd75-40eb-b22c-5b09661fab8f.png align="center")

---

### Brief explanation

The `tar -xJvf` command on Fedora, or any Linux system, is used to extract the contents of a tarball archive file that has been compressed with the XZ compression format.

Let's break this command down:

* tar: tarball archive files command;
    
* \-x: Extract files;
    
* \-J: Use the XZ compression format;
    
* \-v: Display the names of the files as they are extracted;
    
* \-f: File that you want to extract.
    

---

## Check extracted files

```plaintext
ls /opt/Telegram/
```

Output

```apache
[elitebughunter@192 ~]$ ls /opt/Telegram/
Telegram  Updater
```

---

### Brief explanation

The `/opt/telegram` is the destination directory where we want to move the "Telegram" directory. `/opt` is a common location for installing optional or third-party software on Linux systems.

This is a common method for organizing and installing software on Linux systems. After moving, the software installed in "/opt/telegram" can be run from there, and it may require administrative privileges due to the use of sudo.

---

## Create a symbolic link

```plaintext
sudo ln -sf /opt/Telegram/Telegram /usr/bin/telegram
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699270275255/d13378f9-257d-4daa-9f3d-1ec4e645daec.png align="center")

The command `sudo ln -sf /opt/Telegram/Telegram /usr/bin/telegram` creates a symbolic link from the `/usr/bin/telegram` location to the /opt/Telegram/Telegram binary executable file.

So, when we run sudo ln -sf /opt/telegram/Telegram /usr/bin/telegram, we are creating a symbolic link named `telegram` in the `/usr/bin` directory that points to the Telegram executable in `/opt/Telegram/Telegram`." This allows us to run the Telegram application from the command line by simply typing telegram.

---

## Check installation

### Executable file's path

```plaintext
which telegram
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697940983391/c5a3a508-e550-4e42-813a-bbccc0d26583.png align="center")

---

## Run Telegram

```plaintext
telegram
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697941121021/d54a7dfd-477e-4afa-9593-7f55b993da6d.png align="center")

---

## Done

---

## Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

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