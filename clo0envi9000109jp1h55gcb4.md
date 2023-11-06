---
title: "How to Install VS Code on Fedora  38: A Step-by-Step Guide"
datePublished: Sat Oct 21 2023 19:00:50 GMT+0000 (Coordinated Universal Time)
cuid: clo0envi9000109jp1h55gcb4
slug: how-to-install-vs-code-on-fedora-38-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/1bNQVGzuy0U/upload/1c14b211386f0eb733ecd2533d4c7b3d.jpeg
tags: linux, vscode, fedora, linux-for-beginners, alexandrecalaca

---

`Revisited and updated on November 06th, 2023.`

---

## Visual Studio Code

Visual Studio Code is an Extensible and customizable code editor developed by Microsoft.

Besides, it is free, open-source code and It has gained immense popularity among developers and is widely used for a variety of programming languages and development tasks. VS Code is available. It is a terminal emulator for Linux and Unix-like operating systems.

![Easily use extensions in VS Code](https://code.visualstudio.com/assets/images/Hundreds-of-Extensions.png align="left")

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

By importing a `Microsoft GPG key` and creating a new repository configuration for the Visual Studio Code, let's use the `dnf` package manager to install Visual Studio Code.

---

## Import a Microsoft GPG

This step is to ensure we import the `GNU Privacy Guard` public key into the system.

```plaintext
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699267936924/5ca41d4c-4262-4d2d-83a7-dd417de78694.png align="center")

`rpm` is the Red Hat Package Manager, a tool used for managing software packages on Red Hat-based Linux distributions, such as Red Hat Enterprise Linux, CentOS, and Fedora.

The `--import` is an option for the rpm tool, indicating that you want to import a GPG key.

---

## Create a repository configuration file for VS Code

```plaintext
udo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697912727889/1bacffac-66a9-4e5b-beb1-47bc9a4cf5a4.png align="center")

This command creates a repository configuration file for Visual Studio Code, called `vscode.repo`, in the `/etc/yum.repos.d/` directory.

It makes it available for installation and updates via the `YUM` package manager on your Linux system.

The configuration file specifies the repository's name, location, whether it's enabled, and how to perform GPG signature checks on the packages.

---

## Check for updates

```plaintext
dnf check-update
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697913778623/9e0c6c95-bf40-4d74-9555-b4b259eea2b2.png align="center")

The `dnf check-update` command contacts the configured software repositories to check if there are any updates available for the installed packages.

It doesn't perform any actual updates, it merely checks if there are updates available and provides a list of available updates.

---

## Install Visual Sutdio Code

```plaintext
sudo dnf install code
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697914184487/871dd6ed-acd4-4464-a5a4-305934407b78.png align="center")

---

## Check installation

### Version

```apache
code --version
```

Output

```plaintext
[phunter@192 ~]$ code -v
1.83.1
f1b07bd25dfad64b0167beb15359ae573aecd2cc
x64
```

---

### Executable file's path

```apache
which code
```

Output

```plaintext
[phunter@192 ~]$ which code
/usr/bin/code
```

---

## Open Visual Studio Code

```plaintext
code
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697914527650/28244aac-2a88-43c4-b86e-055c6f1c0d58.png align="center")

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