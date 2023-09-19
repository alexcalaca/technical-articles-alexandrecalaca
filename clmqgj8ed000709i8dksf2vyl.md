---
title: "How to install Google Chrome on Linux Mint 21 vanessa via the terminal emulator"
datePublished: Tue Sep 19 2023 15:15:49 GMT+0000 (Coordinated Universal Time)
cuid: clmqgj8ed000709i8dksf2vyl
slug: how-to-install-google-chrome-on-linux-mint-21-vanessa-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695135945372/0f0da193-8dd9-40cd-886e-3901b124e555.jpeg
tags: tutorial, ubuntu, linux

---

---

## Google Chrome

Google Chrome browser was first publicly released, officially as a beta version, on September 2, 2008, for Windows XP and newer, and with support for 43 languages, and later as a "stable" public release on December 11, 2008.

The idea was to innovate the web and the browser was built on the existing technologies. Google chrome was developed keeping in mind to build something more than a browser and so it was developed with a lot of web applications in mind.

---

## Check your system

Make sure you have Linux Mint:

In the terminal

```plaintext
lsb_release -a
```

Output

```plaintext
lsb_release -a
No LSB modules are available.
Distributor ID:	Linuxmint
Description:	Linux Mint 21
Release:	21
Codename:	vanessa
```

---

## Update package manager repository information

```apache
sudo apt update
```

This command refreshes the data about available packages and their versions from the online repositories, ensuring that your system has the most up-to-date information about software packages that can be installed or upgraded.

So, saying that it updates the package manager repository is an accurate description.

---

## Install wget

```apache
sudo apt -y install wget
```

`wget` is a free GNU command-line utility tool used to download files from the internet. It supports HTTP, HTTPS, and FTP protocols.

`wget` has been designed for robustness over slow or unstable network connections; if a download fails due to a network problem, it will keep retrying until the whole file has been retrieved.

It is capable of downloading multiple files, resuming downloads and even mirroring a remote site.

---

## Download the .deb package

```apache
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

.deb is the format, as well as extension of the software package format for the Debian Linux distribution and its derivatives.

So, deb is an abbreviation for Debian package, as opposed to source package.

---

## Install

```apache
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

`dpkg` stands for "Debian Package." It is a package management system used on Debian-based Linux distributions, including Ubuntu, Linux Mint, and Debian itself.

`dpkg` is responsible for the installation, configuration, and removal of software packages on your Linux system.

---

## Solve possible dependencies

```apache
sudo apt install -f
```

The `sudo apt install -f` command is used to fix and resolve package dependency issues on a Debian-based Linux system, such as Ubuntu or Linux Mint.

The `-f` parameter (or `--fix-broken`tells apt to attempt to fix any broken dependencies in the currently installed packages.

It tries to find and install any missing dependencies for packages that are marked as broken or have unresolved dependencies. It removes or purges packages that are in an inconsistent or broken state if necessary. It resolves conflicts and issues that prevent packages from being configured properly.

Running `sudo apt install -f` is a common step to take when you encounter errors related to package dependencies, installation, or configuration. It can help ensure that your system's package database is in a consistent and working state.

This command can be particularly useful after installing or upgrading packages manually using `dpkg`, as it helps to resolve any issues that may arise due to missing or broken dependencies.

---

## Check installation

### Location of the executable file

```apache
which google-chrome
```

Output

```apache
/usr/bin/google-chrome
```

The `which` command in Linux is used to determine the location of an executable file associated with a given command or program.

When you run which followed by a command or program name, it tells you the full path to the executable file that would be executed if you were to run that command in the current environment.

---

### Version

```apache
google-chrome --version
```

Output

```apache
Google Chrome 117.0.5938.62
```

The `--version` option is a common command-line option used in many Unix-like and Linux programs to display information about the version of the software.

When you run a command followed by --version, the program typically responds by printing its version information to the terminal.

---

## Test

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695127521910/cde07c24-d4e6-40c7-bd2b-3ea4cf2aa1a5.png align="center")

---

## Done

---

## **Celebrate**

You've made it!

![Dwight Schrute Celebrating The Office GIF | GIFDB.com](https://gifdb.com/images/high/dwight-schrute-celebrating-the-office-0lsxme8tei1ydjyr.gif align="left")

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