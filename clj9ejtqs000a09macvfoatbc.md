---
title: "How to install Okular Pdf Viewer on Ubuntu and any Debian-based distro"
datePublished: Sat Jun 24 2023 02:49:05 GMT+0000 (Coordinated Universal Time)
cuid: clj9ejtqs000a09macvfoatbc
slug: how-to-install-okular-pdf-viewer-on-ubuntu-and-any-debian-based-distro
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687574820998/42d67aa7-1079-48fa-8dec-d1beab35d022.png
tags: ubuntu, linux, debian, deepin

---

---

## Problem

How to install `Okular Pdf Viewer` on Ubuntu and any Debian-based distro

---

## Pre steps

* Check your operating system;
    
* Check if your operating system is Debian-based.
    

---

### Check your OS

#### lsb\_release

The command "lsb\_release -a" is used to display information about the Linux Standard Base (LSB) and distribution-specific information of your Linux system.

The "lsb\_release" command is useful for identifying the distribution and its version in a standardized manner, particularly if you are writing scripts or need to retrieve distribution information programmatically.

In the terminal

```apache
lsb_release -a
```

The output should be something like this

```apache
No LSB modules are available.
Distributor ID: Deepin
Description:    Deepin 20.7.1
Release:        20.7.1
Codename:       apricot
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687569384827/ae7a581e-9ec9-4fdd-baa5-5254a9f317fc.png align="center")

---

#### os-release

The command "cat /etc/os-release" is used to display the contents of the "/etc/os-release" file, which contains information about the operating system distribution.

The "/etc/os-release" file is commonly used by various system utilities and scripts to determine the distribution and retrieve specific information about the operating system.

In the terminal

```apache
cat /etc/os-release
```

Your output should be something like this

```apache
PRETTY_NAME="Deepin 20.7.1"
NAME="Deepin"
VERSION_ID="20.7.1"
VERSION="20.7.1"
VERSION_CODENAME="apricot"
ID=Deepin
HOME_URL="https://www.deepin.org/"
BUG_REPORT_URL="https://bbs.deepin.org/"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687569637090/70cc8220-890b-436f-8c08-3a885531a6f6.png align="center")

---

### Debian-based distro

In the terminal

```apache
cat /etc/debian_version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687569882413/6bf2ea0e-16d5-4d55-8cce-4ae09077dc13.png align="center")

---

## Steps

* Install via apt;
    
* Confirm installation;
    
* Run it.
    

---

### Install via apt

In Linux, `apt` (short for Advanced Package Tool) is a command-line package management system commonly used in Debian-based distributions, such as Ubuntu.

It provides a convenient and simplified way to install, upgrade, and remove software packages from the command line, making it an essential tool for system administration and software management.

In the terminal

```apache
sudo apt install okular
```

Initial output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687570065429/cb9b8e57-af93-44d6-8f59-560a63865610.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687570032848/83974ca5-eef2-4742-a098-932daf978a33.png align="center")

---

### Confirm installation via which

The "which" command in Linux is used to locate the executable file associated with a given command or program. It helps you determine the path to the binary file that will be executed when you run a particular command.

When you run the "which" command followed by the name of a command, it searches the directories listed in the "PATH" environment variable to find the corresponding executable file.

In the terminal

```apache
which okular
```

output

```apache
/usr/bin/okular
```

---

### Confirm installation via dpkg

The "dpkg -s" command is useful for checking the status of a specific package, verifying its installation, and retrieving detailed information about it, including its version and description.

```apache
dpkg -s okular
```

Initial output

```apache
Package: okular
Status: install ok installed
Priority: optional
Section: graphics
Installed-Size: 13132
Maintainer: Debian Qt/KDE Maintainers <debian-qt-kde@lists.debian.org>
Architecture: amd64
Version: 4:17.12.2-2.2+rb1
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687570271717/32ba4a79-a96b-4177-900b-aae7f25bc650.png align="center")

---

## Run

```apache
okular & disown 
```

output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687570485636/e6b24c22-dc13-4404-af9a-5d8356de207b.png align="center")

"okular" is the command to launch the Okular document viewer application.

The "&" symbol at the end of the command tells the shell to run Okular in the background, allowing you to continue using the terminal.

"disown" is used to detach the Okular process from the terminal session. This prevents the process from being terminated when you close the terminal.

After running this command, Okular should launch in the background, and you can continue using the terminal for other commands without Okular's output or messages interfering.

---

### **Be happy**

You got here. Way to go!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's connect**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome. By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---