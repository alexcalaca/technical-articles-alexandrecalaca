---
title: "How to set up Docker on Fedora 38 via the terminal emulator?"
datePublished: Mon Nov 06 2023 12:51:41 GMT+0000 (Coordinated Universal Time)
cuid: clomwiryd000h09l8hls8hlb9
slug: how-to-set-up-docker-on-fedora-38-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jOqJbvo1P9g/upload/a46e81c5c1ed7fa40c9ef9daff6ce2e6.jpeg
tags: docker, web-development, containers, fedora, alexandrecalaca

---

---

## **Docker**

Docker is a platform for developing, shipping, and running applications in containers.

Containers are lightweight, portable, and self-sufficient units that can package an application and its dependencies, including libraries and configuration files, into a single, consistent environment.

This allows developers to create, deploy, and manage applications more efficiently, regardless of the underlying infrastructure.

---

**Let's get down to business**

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

## Install dependencies

```apache
sudo dnf -y install dnf-plugins-core
```

---

## Add a YUM repo for Docker

```ruby
sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```

Your output should look something like the following:

```basic
[elitebughunter@192 ~]$ sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
Adding repo from: https://download.docker.com/linux/fedora/docker-ce.repo
[elitebughunter@192 ~]$ 
```

---

### Brief explanation

`config-manager`: This is a DNF subcommand used for managing repository configurations.

`--add-repo`: This flag indicates that you want to add a new repository to the system.

[`https://download.docker.com/linux/fedora/docker-ce.repo`](https://download.docker.com/linux/fedora/docker-ce.repo): This is the URL of the Docker repository configuration file. By adding this repository, you make Docker-related packages and updates available for installation and management through DNF on your Fedora system.

---

## Check repo

```ruby
sudo dnf repolist
sudo dnf repolist | grep docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699274355462/9751022c-9160-4777-b70d-5e1b930dd418.png align="center")

---

## Install Docker Engine, containerd, and Docker Compose

```plaintext
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699274428466/3e00a753-b1a2-4c27-b1ee-6c5bda7340a1.png align="center")

---

## Check installation

```ruby
docker --version
which docker
docker --help
```

Your output should look something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699069098421/d23583c9-7b07-49bd-9876-d9eee38f1665.png?auto=compress,format&format=webp align="left")

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

## Start Docker

```ruby
sudo systemctl start docker
```

---

### Check the status

```plaintext
sudo systemctl status docker
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699274858447/aa10bcb9-935f-47a2-8513-e363fa3e86bf.png align="center")

---

## Run Hello-world

```ruby
sudo docker run hello-world
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699274932396/0589559a-70b1-416e-ab73-732aef8e2a4c.png align="center")

---

## Done

You have now successfully installed and started Docker Engine.

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