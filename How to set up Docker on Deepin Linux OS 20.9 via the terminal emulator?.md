---
title: "How to set up Docker on Deepin Linux OS 20.9 via the terminal emulator?"
datePublished: Sat Nov 04 2023 03:46:35 GMT+0000 (Coordinated Universal Time)
cuid: cloji62fi000109l7bsms4bha
slug: how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HjBOmBPbi9k/upload/259aeb74eaf5742d45d0ab4e2f7850ef.jpeg
tags: docker, linux-for-beginners, linux-basics, deepin, linux-commands

---

---

## Docker

Docker is a platform for developing, shipping, and running applications in containers.

Containers are lightweight, portable, and self-sufficient units that can package an application and its dependencies, including libraries and configuration files, into a single, consistent environment.

This allows developers to create, deploy, and manage applications more efficiently, regardless of the underlying infrastructure.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## **Check your OS (optional)**

This step is just to make sure you have **Deepin Linux installed.**

```plaintext
lsb_release -a
hostnamectl
cat /etc/os-release
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772856976/3bf1885b-0024-4886-a8b3-d6a891175205.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Update packages info

```apache
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install dependencies

```plaintext
sudo apt install apt-transport-https ca-certificates gnupg2 curl software-properties-common -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699067963929/56071372-7015-43d3-8a01-090710879b4a.png align="center")

---

## Download Docker GPG (GNU Privacy Guard) key

```plaintext
sudo curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699068145673/8499444c-cce9-47a7-bfd0-6032a0084383.png align="center")

`Curl` is a command-line tool for transferring data with URLs. In this context, it is used to fetch data from the specified URL.

---

## Check Docker GPG key

```plaintext
sudo apt-key fingerprint 0EBFCD88
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699068387532/61869482-ece6-4238-a531-c207764ecd77.png align="center")

`0EBFCD88` is the key ID or key fingerprint of the GPG key for which you want to retrieve information. In this case, `0EBFCD88` is typically the GPG key associated with the Docker repository.

The `sudo apt-key fingerprint` command is used to display the fingerprint of a GPG key that has been added to the APT (Advanced Package Tool) keyring on a Debian-based Linux system. The fingerprint is a unique identifier for a GPG key, and it's used to verify the authenticity of the key.

---

## Add a new entry to the repository

```plaintext
printf 'deb [arch=amd64] https://download.docker.com/linux/debian buster stable\n'| sudo tee /etc/apt/sources.list.d/docker-ce.list
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699068608052/fa762913-fd41-4316-ae4b-6d9b58ad611a.png align="center")

---

## Update package info

```apache
sudo apt-get update
```

---

## Install Docker

```plaintext
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699068803117/8ee3497a-ba5e-491d-8a8d-4fe849aef852.png align="center")

`docker-ce` is the package name for Docker CE (Community Edition), which is the version of Docker designed for community use and development environments.

Docker CE Command Line Interface (CLI) is available through the package `docker-ce-cli`. It provides the command-line tools for working with Docker containers and images.

[`containerd.io`](http://containerd.io) is the package name for `containerd`, which is an essential component of the Docker runtime that manages containers and provides a basic infrastructure for container execution.

---

## Check installation

```plaintext
docker --version
which docker
docker --help
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069098421/d23583c9-7b07-49bd-9876-d9eee38f1665.png align="center")

---

## Check status

```plaintext
sudo systemctl status docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069175809/1666172f-5c91-4025-873c-86eedade2ac7.png align="center")

1. The command used to manage and control system services on Linux systems that use `systemd` as their init system is `systemctl`.
    
    `systemd` is a system and service manager commonly used in modern Linux distributions.
    
    ---
    

## Configure Docker hello-world

```plaintext
sudo docker pull hello-world
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069445042/631ff266-bcc8-409c-8645-38bc70f1f5e3.png align="center")

---

## Run Docker hello-world

```plaintext
sudo docker run hello-world
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069445042/631ff266-bcc8-409c-8645-38bc70f1f5e3.png align="center")

---

## **Done**

---

## **Celebrate**

![Happy Season 2 GIF by The Office - Find & Share on GIPHY](https://media2.giphy.com/media/jQediRqu0oLXNdjDbN/giphy.gif?cid=6c09b952sfrdnl666a3hp1aeryp278rp59g3w8aj33myfbux&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g align="left")

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
