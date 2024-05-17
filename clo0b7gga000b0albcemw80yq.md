---
title: "Installing lsb_release on Fedora: How to Check Your Linux Distribution Version"
datePublished: Sat Oct 21 2023 17:24:05 GMT+0000 (Coordinated Universal Time)
cuid: clo0b7gga000b0albcemw80yq
slug: installing-lsbrelease-on-fedora-how-to-check-your-linux-distribution-version
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/vU2MmvDCmUo/upload/52ac8051250423eb8c8e7a5f592320ce.jpeg
tags: tutorial, linux, fedora, linux-for-beginners, linux-basics

---

---

## lsb\_release

### Definition

`lsb_release` is a command-line utility commonly found in Linux distributions that adhere to the Linux Standard Base (LSB). The LSB is a standardization initiative that aims to increase compatibility between different Linux distributions by defining a common set of libraries and conventions.

---

### Functionality

The `lsb_release` command provides information about the Linux distribution you're using, including details such as the distributor's ID, description, release number, and code name.

---

### Real example

Typically, you can use `lsb_release` to retrieve information about your Linux distribution, which can be useful for scripting and determining the specifics of the operating system you're working with. This information can be valuable when you need to write scripts or code that should behave differently depending on the Linux distribution or version.

For example, you might use `lsb_release` to determine whether you're on Ubuntu, Fedora, Debian, or another distribution, and then tailor your script or program accordingly.

---

### Linux distributions

It's important to note that not all Linux distributions include `lsb_release` by default, and some may provide similar information using other methods or commands. The availability and functionality of `lsb_release` can vary between distributions.

---

## **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

By using the `dnf` package manager, Let's install the `redthat_lsb_core`

---

## DNF Package manager

### Meaning

`DNF` stands for "Dandified Yum." It is the next-generation package manager used in various Linux distributions, including Fedora and Red Hat Enterprise Linux (RHEL).

---

### Features

DNF was introduced as a replacement for the Yum package manager, and it offers improved performance, dependency resolution, and a more user-friendly command-line interface for package management tasks.

---

### Name origin

The name "Dandified Yum" is a play on words and a nod to Yum, which stands for "Yellowdog Updater, Modified."

---

## Open the terminal

---

## Update Fedora

```apache
sudo dnf update
```

Before installing any new packages, it's a good idea to update your system to make sure you have the latest package information and security updates.

---

## Install the package

Open the terminal and run the following command:

```apache
sudo dnf install redhat-lsb-core
```

The output will look something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697908466513/411c9f99-1db8-4ae9-94f5-831c30edc912.png align="center")

---

## Check installation

### Version

```apache
lsb_release --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697908818841/5161b019-4163-4e3a-9247-1a34b2599683.png align="center")

---

### Executable file's path

```apache
which lsb_release
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697908833108/23ea32fe-d779-42ca-8365-a52361947310.png align="center")

---

## Retrieve OS information

```plaintext
lsb_release -a
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697908558448/3313c8c6-f769-4476-b763-e5ab626805c6.png align="center")

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