---
title: "How to install Docker-compose on Deepin OS 20.9 or any other Debian-based Linux distribution via the terminal emulator?"
datePublished: Fri Sep 15 2023 04:23:32 GMT+0000 (Coordinated Universal Time)
cuid: clmk3gzv2000309l2ffm45e4e
slug: how-to-install-docker-compose-on-deepin-os-209-or-any-other-debian-based-linux-distribution-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694751769517/cc5b6b62-d2e3-48c6-aac0-3f4ec562c852.png
tags: tutorial, ubuntu, linux, docker, debian

---

---

## Check your operating system

[Click here](https://blog.alexandrecalaca.com/how-to-determine-if-your-linux-distribution-is-debian-based) in order to determine if your operating system is Debian-Based.

Knowing if your operating system is Debian-based is crucial for efficient system management and software compatibility.

If you prefer, you can copy and paste the following link into your address bar:

[https://blog.alexandrecalaca.com/how-to-determine-if-your-linux-distribution-is-debian-based](https://blog.alexandrecalaca.com/how-to-determine-if-your-linux-distribution-is-debian-based)

---

## Update package repository information

```plaintext
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Download Docker-compose binary

```apache
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694751354481/f0b3fede-9b48-42ca-90c5-1cb5ea6cb237.png align="center")

The command downloads the Docker Compose binary for your specific operating system and architecture from GitHub and places it in the `/usr/local/bin` directory, making it accessible system-wide.

---

## Make it executable

```apache
sudo chmod +x /usr/local/bin/docker-compose
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694751393818/1c8d64d6-acd1-4c2a-8e20-d7ec84c27ffc.png align="center")

The command `sudo chmod +x /usr/local/bin/docker-compose` is making the Docker Compose binary executable.

This step is necessary because, by default, files downloaded from the internet are not executable for security reasons.

By granting execute permission, you enable the system to run the Docker Compose binary as a program when you use it in the command line.

---

## Verify the installation

### Version

```apache
docker-compose --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694751451488/f679e4f7-5232-4a85-9fcd-08c46d0ef105.png align="center")

---

### Through executable path

```apache
which docker-compose
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694751600820/b6963bc6-29d9-49af-be04-3a966a7d2d7d.png align="center")

---

## Test

```plaintext
docker-compose up
```

Since I did not provide any arguments after the preposition up, it should return something like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694751722238/7d6f2c26-ef51-4e0a-912e-fce3b95f6444.png align="center")

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