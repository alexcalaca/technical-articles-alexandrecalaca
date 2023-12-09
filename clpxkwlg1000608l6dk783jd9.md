---
title: "Installing Docker Desktop and Docker Compose on Pop!_OS 22.04: Comprehensive guide"
datePublished: Sat Dec 09 2023 04:51:41 GMT+0000 (Coordinated Universal Time)
cuid: clpxkwlg1000608l6dk783jd9
slug: installing-docker-desktop-and-docker-compose-on-popos-2204-comprehensive-guide
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/t5OL-MfIqLc/upload/eadf484efe91310bf78061369c50f83b.jpeg
tags: linux, docker, docker-compose, linux-for-beginners, popos, alexandrecalaca

---

---

## **Docker**

Docker is a platform for developing, shipping, and running applications in containers.

Containers are lightweight, portable, and self-sufficient units that can package an application and its dependencies, including libraries and configuration files, into a single, consistent environment.

This allows developers to create, deploy, and manage applications more efficiently, regardless of the underlying infrastructure.

---

## **Docker Desktop**

Docker Desktop is a desktop application that provides an integrated development environment for Docker.

It allows developers to create, run, and manage Docker containers on their local machines with ease.

Two important characteristics are:

**Docker Engine**: Docker Desktop includes the Docker Engine, which is the core component of Docker, allowing you to create and run containers on your local system.

**Container Management**: It provides a graphical user interface (GUI) for managing containers and images, making it easier to build, run, and monitor containerized applications.

---

## **Let's get down to business**

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="left")

---

### **Check your OS (optional)**

This step is just to make sure you have `Pop!_OS` installed.

```plaintext
uname -a
hostnamectl
lsb_release -a
cat /etc/os-release
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

---

## **Update packages info**

```plaintext
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install Docker Engine

Make sure you have Docker Engine installed by [clicking here](https://blog.alexandrecalaca.com/installing-docker-engine-on-popos-2204-comprehensive-guide) or on the following link:

[https://blog.alexandrecalaca.com/installing-docker-engine-on-popos-2204-comprehensive-guide](https://blog.alexandrecalaca.com/installing-docker-engine-on-popos-2204-comprehensive-guide?showSharer=true)

---

## Go to Docker Desktop installation's page

[Click here](https://docs.docker.com/desktop/install/ubuntu/) or on the following link:

[https://docs.docker.com/desktop/install/ubuntu/](https://docs.docker.com/desktop/install/ubuntu/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702095896331/33e22857-7047-4b4f-871a-a891588fdb7a.png align="center")

---

## Download the Deb package

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702095966977/67f7f595-ae5a-4faa-8b98-575a7db7820b.png align="center")

---

## Install the package

```plaintext
sudo apt install ./Downloads/docker-desktop-4.26.0-amd64.deb 
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702096101350/288fe16a-f061-4413-b3f0-8f9471eb60c4.png align="center")

---

## Error message

At the end of the installation process, `apt` displays an error due to installing a downloaded package. Just ignore it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702096217996/4448856c-76e3-41ae-8bc9-72bcc9e85fc9.png align="center")

---

## Launch Docker Desktop

```plaintext
systemctl --user start docker-desktop
```

---

## Accept Docker subscription

Accept **Docker Subscription Service Agreement.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702096426718/aa55fdfa-8616-4e0c-b802-6cb4b398ac5d.png align="center")

---

## Sign up (optional)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702096465418/37c00dd2-6f8d-42aa-a135-b5d77eae4bd9.png align="center")

---

## Check all Docker versions

The Docker Desktop installer updates Docker Compose and the Docker CLI binaries on the host. It installs Docker Compose V2 and gives users the choice to link it as docker-compose from the Settings panel.

```plaintext
docker compose version
docker --version
docker version
```

output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702096833306/21f28470-94e2-4549-9889-397973764e03.png align="center")

---

## Check Docker status

```plaintext
sudo systemctl status docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702097184895/78eaab9a-1c77-4c6e-ba11-f7379298599f.png align="center")

The command is used to manage and control system services on Linux systems that use systemd as their init system is systemctl.

systemd is a system and service manager commonly used in modern Linux distributions.

---

## Enable Docker Desktop on login

```plaintext
systemctl --user enable docker-desktop
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702097338473/3832f337-60e1-4042-a446-7fed8e83d238.png align="center")

---

## **Done**

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

## **Let's network**

* [**Github**](https://github.com/alexcalaca)
    
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