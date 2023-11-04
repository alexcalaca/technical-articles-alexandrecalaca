---
title: "Installing Telegram on Linux: A comprehensive common guide for all distributions"
datePublished: Sun Oct 22 2023 02:23:37 GMT+0000 (Coordinated Universal Time)
cuid: clo0uhb09000008mibrpy64kj
slug: installing-telegram-on-linux-a-comprehensive-common-guide-for-all-distributions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697936892276/ec68908e-fe67-4025-a9f8-4bbbb4beb713.jpeg
tags: tutorial, linux, linux-for-beginners, linux-basics

---

---

## Telegram

Telegram is a cloud-based instant messaging app and communication platform. It was created by Pavel Durov and his brother Nikolai Durov in 2013. Telegram is known for its focus on security, privacy, and encryption, making it a popular choice for individuals and groups who value secure and private communication.

![Telegram Premium é lançado e custará até R$ 24,90 ao mês](https://static.poder360.com.br/2022/03/telegram-aplicativo-vpn-848x477.jpg align="left")

---

## Check your OS

This step is optional. It's just to make sure you have `Fedora`installed.

---

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

## **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

## Go to the official website

Go to the [official website](https://desktop.telegram.org/) or click directly on the following link: [https://desktop.telegram.org/](https://desktop.telegram.org/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697938023897/f1176cc6-427e-4e16-bfd2-0d2439d319a4.png align="center")

---

## Download Telegram

Click on the **Get TEelegram for Linux x64** button or clicked directly on the following link: [https://telegram.org/dl/desktop/linux](https://telegram.org/dl/desktop/linux)

---

## Extract the file

```plaintext
tar -xJvf ~/Downloads/tsetup.4.10.3.tar.xz
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697939934858/3eee38de-dd75-40eb-b22c-5b09661fab8f.png align="center")

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
ls
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697940374451/582f1536-8ad1-4fd3-a6e1-4bdd3cf5076d.png align="center")

---

## Move Telegram binary

```plaintext
sudo mv Telegram/ /opt/telegram
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697940336763/bd8a6c6f-c1bb-422e-a9fb-0310f1ae43f1.png align="center")

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

So, when we run sudo ln -sf /opt/telegram/Telegram /usr/bin/telegram, we are creating a symbolic link named `telegram` in the `/usr/bin` directory that points to the Telegram executable in "`/opt/telegram/Telegram`." This allows us to run the Telegram application from the command line by simply typing telegram.

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