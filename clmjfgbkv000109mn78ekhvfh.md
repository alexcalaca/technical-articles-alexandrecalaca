---
title: "How to install Docker on Deepin OS 20.7 or any other Debian-based Linux distribution via the terminal emulator?"
datePublished: Thu Sep 14 2023 17:11:10 GMT+0000 (Coordinated Universal Time)
cuid: clmjfgbkv000109mn78ekhvfh
slug: how-to-install-docker-on-deepin-os-207-or-any-other-debian-based-linux-distribution-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HSACbYjZsqQ/upload/cc6acb182cd82f451c0d9971a814a88c.jpeg
tags: tutorial, ubuntu, linux, docker, deepin

---

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

## Docker GPG key:

```apache
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694455639115/db140838-ae53-4b8c-81a8-e9e5fff7aef8.png align="center")

---

## Docker repository for GPG key

```apache
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694456122993/5a92ef1e-a3fa-4f2c-8680-7a4ef8311f76.png align="center")

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