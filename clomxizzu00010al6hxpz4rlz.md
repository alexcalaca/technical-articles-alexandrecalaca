---
title: "How to set up Docker Desktop on Fedora 38"
datePublished: Mon Nov 06 2023 13:19:51 GMT+0000 (Coordinated Universal Time)
cuid: clomxizzu00010al6hxpz4rlz
slug: how-to-set-up-docker-desktop-on-fedora-38
tags: software-development, linux, docker, fedora, alexandrecalaca

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

#### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

## **Check your OS (optional)**

This step is just to ensure you have **Fedora 38 Linux installed. You can pick up one command or you can use them all.**

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

## Install Docker

**Follow the steps** [**here**](https://blog.alexandrecalaca.com/how-to-set-up-docker-on-fedora-38-via-the-terminal-emulator) **or through the following link:** [https://blog.alexandrecalaca.com/how-to-set-up-docker-on-fedora-38-via-the-terminal-emulator](https://blog.alexandrecalaca.com/how-to-set-up-docker-on-fedora-38-via-the-terminal-emulator)

---

## Go to the instructions page

```ruby
https://docs.docker.com/desktop/install/fedora/
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699275428099/732f1c51-ed1b-45ba-9d12-3fb2fefb95ac.png align="center")

---

## Download the RPM package

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699275548811/4d976032-e284-46de-b68f-e2eeed8bbf23.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699275592446/dee2ac7f-3def-4cc6-b9d2-c1b672c0914a.png align="center")

---

## Install the package

```ruby
sudo dnf install ~/Downloads/docker-desktop-4.25.0-x86_64.rpm
```

---

## Confirm installation

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699276354939/d62256ae-ce68-4e22-8401-0b27256e6e45.png align="center")

After the confirmation, you should see something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699275764547/edc17a7a-82a7-4a44-acf2-d4ab08b628a7.png align="center")

---

## Check installation

The Docker Desktop installer updates Docker Compose and the Docker CLI binaries on the host. It installs Docker Compose V2 and gives users the choice to link it as docker-compose from the Settings panel.

Docker Desktop installs the new Docker CLI binary that includes cloud-integration capabilities in

```ruby
docker compose version
docker --version
docker version
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699276468532/671e80eb-f397-4fc3-aaf3-cd738b2e5d4f.png align="center")

---

## Check Docker status

```plaintext
sudo systemctl status docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699274690769/9876f60d-fbda-4fbb-80d5-f86b213789d3.png align="center")

The command is used to manage and control system services on Linux systems that use `systemd` as their init system is `systemctl`.

`systemd` is a system and service manager commonly used in modern Linux distributions.

---

## Done

You have now successfully installed and started Docker Desktop.

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