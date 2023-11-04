---
title: "How to configure Docker Desktop on Deepin Linux OS 20.9"
datePublished: Sat Nov 04 2023 04:35:51 GMT+0000 (Coordinated Universal Time)
cuid: clojjxfdr000c08jx9a3v4039
slug: how-to-configure-docker-desktop-on-deepin-linux-os-209
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/0blbblsyf3o/upload/1aa42981a266ebe1e8b545a60057e464.jpeg
tags: linux, docker, linux-for-beginners, linux-basics, deepin

---

---

## **Docker**

Docker is a platform for developing, shipping, and running applications in containers.

---

## Docker Desktop

  
Docker Desktop is a desktop application that provides an integrated development environment for Docker.

It allows developers to create, run, and manage Docker containers on their local machines with ease.

Two important characteristics are:

**Docker Engine**: Docker Desktop includes the Docker Engine, which is the core component of Docker, allowing you to create and run containers on your local system.

**Container Management**: It provides a graphical user interface (GUI) for managing containers and images, making it easier to build, run, and monitor containerized applications.

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772856976/3bf1885b-0024-4886-a8b3-d6a891175205.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Update packages info

```plaintext
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install Docker

**Follow the steps** [**here**](https://blog.alexandrecalaca.com/how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator) **or through the following link:** [https://blog.alexandrecalaca.com/how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator](https://blog.alexandrecalaca.com/how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator)

---

## Go to the main Docker page

```plaintext
https://docs.docker.com/desktop/install/debian/
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699071940731/82caca45-cfbd-403d-bac4-7b93c57f692b.png align="center")

---

## Download the .deb package file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699071978977/ff214c8d-66ce-4c78-a8c1-b008b25f58b8.png align="center")

---

## See Docker-desktop .deb file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699071037965/ad3a745d-ccff-4dbb-9407-0fa6bf6ea590.png align="center")

---

## Install Docker-desktop

Double-click on the file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699070985446/e6652346-87b1-40e6-b3d3-343c827b3bf5.png align="center")

---

## Confirm installation

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699071084422/371f834a-a3f6-4fb6-b307-f880eb5e69c2.png align="center")

---

## Check installation

```plaintext
docker compose version
docker --version
docker version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699071601191/dbd8b5d4-89ea-434f-bf5c-c50cb9a47a2d.png align="center")

---

## Launch Docker desktop

```plaintext
systemctl --user start docker-desktop
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699071370611/0153d347-9abd-48e0-b6e3-084686fc5770.png align="center")

---

## Check installation

```plaintext
docker --version
which docker
docker --help
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069098421/d23583c9-7b07-49bd-9876-d9eee38f1665.png?auto=compress,format&format=webp align="left")

---

## Check status

```plaintext
sudo systemctl status docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069175809/1666172f-5c91-4025-873c-86eedade2ac7.png?auto=compress,format&format=webp align="left")

1. The command used to manage and control system services on Linux systems that use `systemd` as their init system is `systemctl`.
    
    `systemd` is a system and service manager commonly used in modern Linux distributions.
    
    ---
    

## Configure Docker hello-world

```plaintext
sudo docker pull hello-world
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069445042/631ff266-bcc8-409c-8645-38bc70f1f5e3.png?auto=compress,format&format=webp align="left")

---

## Run Docker hello-world

```plaintext
sudo docker run hello-world
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069445042/631ff266-bcc8-409c-8645-38bc70f1f5e3.png align="left")

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