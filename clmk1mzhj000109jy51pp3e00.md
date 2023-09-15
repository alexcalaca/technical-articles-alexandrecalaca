---
title: "How to install Docker on Elementary OS 6.1 or any other Ubuntu-based Linux distribution via the terminal emulator?"
datePublished: Fri Sep 15 2023 03:32:12 GMT+0000 (Coordinated Universal Time)
cuid: clmk1mzhj000109jy51pp3e00
slug: how-to-install-docker-on-elementary-os-61-or-any-other-ubuntu-based-linux-distribution-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HSACbYjZsqQ/upload/33108f1279cec360631e9eb77f7ce043.jpeg
tags: tutorial, ubuntu, programming-blogs, docker, elementary-os

---

---

## Check your operating system

### LSB release

```plaintext
lsb_release -a
```

Output

```apache
lsb_release -a
No LSB modules are available.
Distributor ID:	Elementary
Description:	elementary OS 6.1 Jólnir
Release:	6.1
Codename:	jolnir
```

The `lsb_release -a` command is used to display detailed information about the Linux distribution on your system.

It stands for "Linux Standard Base release" and provides information such as the distribution's name, release number, codename, and more

---

### Linux installed

```plaintext
cat /etc/os-release
```

Output

```apache
cat /etc/os-release 
NAME="elementary OS"
VERSION="6.1 Jólnir"
ID=elementary
ID_LIKE=ubuntu
PRETTY_NAME="elementary OS 6.1 Jólnir"
LOGO=distributor-logo
VERSION_ID="6.1"
HOME_URL="https://elementary.io/"
DOCUMENTATION_URL="https://elementary.io/docs/learning-the-basics"
SUPPORT_URL="https://elementary.io/support"
BUG_REPORT_URL="https://github.com/elementary/triage/issues/new"
PRIVACY_POLICY_URL="https://elementary.io/privacy-policy"
VERSION_CODENAME=jolnir
UBUNTU_CODENAME=focal
```

The `cat /etc/os-release` command in the terminal will display the contents of the `/etc/os-release` file, which contains information about the Linux distribution installed on your system.

if it's Ubuntu-based, you might see something in `ID_LIKE`,  
`UBUNTU_CODENAME` or another attribute.

---

## Update packages info

```apache
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install required dependencies

```apache
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

In summary, the provided command is used to install essential packages and utilities that are commonly required for adding external repositories, securely fetching packages over HTTPS, and managing software sources on an Ubuntu system. These packages are often necessary for setting up and maintaining software on your system.

---

## Add Docker GPG key

```apache
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694455639115/db140838-ae53-4b8c-81a8-e9e5fff7aef8.png align="center")

---

## Add the Docker repository to the apt sources list

```apache
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

The command constructs a repository source entry for Docker, based on your distribution's codename (obtained using lsb\_release -cs), and then writes that entry to the /etc/apt/sources.list.d/docker.list file.

This is how you add a Docker repository source to your APT configuration on a Debian-based system, ensuring that APT can find and install Docker packages from the specified repository.

---

## Update package info

```apache
sudo apt-get update
```

---

## Install docker

```plaintext
sudo apt-get install docker-ce
```

then

```plaintext
sudo apt-get install docker-ce-cli containerd.io
```

Output

---

## Check installation

### Through version

```apache
docker --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694456845055/2baddf3d-72dd-47fc-875d-7d62608398b4.png align="center")

---

### Through executable path

```plaintext
which docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694710972784/5445c26e-82d4-4647-b728-ff5d49fa585f.png align="center")

---

## Check status

```apache
sudo systemctl status docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694456940777/941eb832-97b1-4a3d-aac5-7fb9d51cbe55.png align="center")

---

## Restart the Operating System

---

## Test

```plaintext
 sudo docker run hello-world
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