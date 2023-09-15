---
title: "How to install .deb files on Elementary OS 6.1 via the terminal emulator?"
datePublished: Fri Sep 15 2023 01:55:30 GMT+0000 (Coordinated Universal Time)
cuid: clmjy6m1c000009l28eqodc0b
slug: how-to-install-deb-files-on-elementary-os-61-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/NLSXFjl_nhc/upload/c09704ae3664e30e98c1415bc422ddeb.jpeg
tags: tutorial, ubuntu, linux, debian

---

---

## .deb file

A `.deb` file is a software package format used primarily by Debian-based Linux distributions, including Debian itself, Ubuntu, and Elementary OS. It serves as a means of packaging and distributing software applications and libraries for easy installation and management on these Linux systems.

---

## Solution

Let's use `Gdebi`.

---

## Gdebi

**GDebi** is a graphical tool for installing Debian (.deb) packages on Debian-based Linux distributions.

It provides a user-friendly interface for installing software packages in the .deb format, making it easier for users who prefer graphical tools over the command line.

The most important characteristic of `gdebi` is Dependency Resolution. `GDebi` checks for and installs any missing package dependencies required by the .deb package being installed. This helps ensure that the software functions correctly after installation.

---

## Update the package information

```plaintext
sudo apt update
```

The sudo apt update command in Linux is used to update the package information for software repositories configured on your system.

---

## Install Gdebi

```plaintext
sudo apt install gdebi
```

---

### Check installation

#### Executable path

```plaintext
which gdebi
which gdebi-gtk
```

---

#### Version

```plaintext
gdebi --version
```

---

#### Run

```plaintext
gdebi-gtk
```

---

#### Installation status

```plaintext
dpkg -l | grep gdebi
```

---

## Install the .deb file

```plaintext
sudo gdebi my_file.deb
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