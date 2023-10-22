---
title: "Installing Git on Fedora 38 with screenshots"
datePublished: Sun Oct 22 2023 19:11:46 GMT+0000 (Coordinated Universal Time)
cuid: clo1uhsbv000409l26cu2cl73
slug: installing-git-on-fedora-38-with-screenshots
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698001797083/db8c9420-4e88-47ca-91c3-fcc45b926bef.png
tags: linux, github, git, fedora, linux-for-beginners

---

---

## Git

Git is a distributed version control system (DVCS) that is widely used in software development and other fields where version management is essential.

It was created by Linus Torvalds in 2005 and is open source, which means it's freely available and widely adopted in both open source and commercial software development.

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

## Open the terminal

---

## **Update Fedora**

Although It's a good practice to ensure your system is up-to-date before installing new software, this is an optional step.

```plaintext
sudo dnf update
```

---

## **Install git**

```plaintext
sudo dnf install git
```

You'll be prompted to enter and confirm the installation.

`Output`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698001474133/7bc22548-2246-4058-ba62-0f7931dc374b.png align="center")

---

## Check installation

### Version

```apache
git --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698001568827/73306764-e359-4f51-9bea-8cf9cacfaa36.png align="center")

---

### Executable file's path

```apache
which git
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698001576522/6ff982b8-bd70-4b14-a2e4-4cdd6bea75d8.png align="center")

---

## Run git

```plaintext
git
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698001584522/f0d202ed-d7f7-4c20-aae4-6bb025235dd8.png align="center")

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