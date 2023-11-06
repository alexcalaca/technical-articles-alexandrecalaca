---
title: "Installing the best screenshot tool on Fedora 38: Flameshot"
datePublished: Mon Nov 06 2023 10:47:48 GMT+0000 (Coordinated Universal Time)
cuid: cloms3gew000c08l2ho4efwbp
slug: installing-the-best-screenshot-tool-on-fedora-38-flameshot
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699267446344/5487fb96-e5e3-42d9-aa4d-1d1406228d5c.jpeg
tags: linux, fedora, linux-for-beginners, linux-basics, alexandrecalaca

---

---

## Flameshot

Flameshot is an open-source screenshot tool for Linux-based operating systems and Windows. It allows you to capture screenshots of your desktop, specific windows, or custom regions, and it provides various annotation and editing features to enhance your screenshots.

Flameshot is a popular choice among Linux users for taking and editing screenshots, and it provides a user-friendly interface for those who need basic screenshot capture and editing capabilities.

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

## Install Flameshot

```plaintext
sudo dnf install flameshot -y
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699266630079/ce4c7683-857d-4e1e-af9c-1afcb69e0fe3.png align="center")

---

## Check installation

### Program's binary

```plaintext
which flameshot
```

Output

```plaintext
[elitebughunter@192 ~]$ which flameshot
/usr/bin/flameshot
```

The `which` command is used to locate the executable file associated with a given command or program. When you run `which` followed by a program's name, it will display the path to the executable file of that program, if it is found in your system's PATH.

For example, when you run `which flameshot`, it searches for the "flameshot" command in the directories listed in your PATH environment variable and tells you the full path to the Flameshot executable.

This is useful for confirming the location of a program's binary if you want to ensure you are running the intended version or if you need to work with the program's files directly.

---

### Version

```plaintext
flameshot --version
```

Output

```plaintext
[elitebughunter@192 ~]$ flameshot --version
Flameshot v12.1.0 (-)
Compiled with Qt 5.15.8
```

Running the `program --version` command is a way to check the version of the program that is installed on your system.

When you run this command, the `program` will display information about its version, which can include details like the version number, build information, and other relevant version-specific details.

---

## Open Flameshot

```plaintext
flameshot gui
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699267342543/56298b43-5868-4b34-bfee-b7552847c509.png align="center")

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