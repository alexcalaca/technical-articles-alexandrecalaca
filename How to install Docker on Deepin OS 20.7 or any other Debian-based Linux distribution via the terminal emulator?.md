---
title: "How to install Docker on Deepin OS 20.7 or any other Debian-based Linux distribution via the terminal emulator?"
datePublished: Thu Sep 14 2023 17:11:10 GMT+0000 (Coordinated Universal Time)
cuid: clmjfgbkv000109mn78ekhvfh
slug: how-to-install-docker-on-deepin-os-207-or-any-other-debian-based-linux-distribution-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HSACbYjZsqQ/upload/cc6acb182cd82f451c0d9971a814a88c.jpeg
tags: tutorial, ubuntu, linux, docker, deepin

---

`Revisited and updated on November 04th, 2023.`

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

```apache
sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

or

```apache
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

In summary, the provided command is used to install essential packages and utilities that are commonly required for adding external repositories, securely fetching packages over HTTPS, and managing software sources on an Ubuntu system. These packages are often necessary for setting up and maintaining software on your system.

---

## Download Docker GPG (GNU Privacy Guard) key

```apache
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694455639115/db140838-ae53-4b8c-81a8-e9e5fff7aef8.png align="center")

---

## Check Docker GPG key

```plaintext
The sudo apt-key fingerprint command is used to display the fingerprint of a GPG key that has been added to the APT (Advanced Package Tool) keyring on a Debian-based Linux system. The fingerprint is a unique identifier for a GPG key, and it's used to verify the authenticity of the key.
```

The output would be something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699068387532/61869482-ece6-4238-a531-c207764ecd77.png align="center")

`0EBFCD88` is the key ID or key fingerprint of the GPG key for which you want to retrieve information. In this case, `0EBFCD88` is typically the GPG key associated with the Docker repository.

The `sudo apt-key fingerprint` command is used to display the fingerprint of a GPG key that has been added to the APT (Advanced Package Tool) keyring on a Debian-based Linux system. The fingerprint is a unique identifier for a GPG key, and it's used to verify the authenticity of the key.

---

## Docker repository for GPG key

```apache
printf 'deb [arch=amd64] https://download.docker.com/linux/debian buster stable\n'| sudo tee /etc/apt/sources.list.d/docker-ce.list
```

Output would be something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699068608052/fa762913-fd41-4316-ae4b-6d9b58ad611a.png align="center")

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
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694456616119/3f2e323a-419e-4c0c-860f-b5d1db432a82.png align="center")

`docker-ce` is the package name for Docker CE (Community Edition), which is the version of Docker designed for community use and development environments.

Docker CE Command Line Interface (CLI) is available through the package `docker-ce-cli`. It provides the command-line tools for working with Docker containers and images.

[`containerd.io`](http://containerd.io) is the package name for `containerd`, which is an essential component of the Docker runtime that manages containers and provides a basic infrastructure for container execution.

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

## Download docker compose

```apache
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694457278122/5705bf38-bbfc-418f-bc1d-bdaf8c699c94.png align="center")

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
