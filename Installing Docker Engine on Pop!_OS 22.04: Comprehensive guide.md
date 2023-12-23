---
title: "Installing Docker Engine on Pop!_OS 22.04: Comprehensive guide"
datePublished: Sat Dec 09 2023 04:18:41 GMT+0000 (Coordinated Universal Time)
cuid: clpxjq5se000108l3gvxchnmf
slug: installing-docker-engine-on-popos-2204-comprehensive-guide
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/SInhLTQouEk/upload/5e85f6c76016abb6eb0d4a93b5771605.jpeg
tags: tutorial, ubuntu, linux, docker, popos, alexandrecalaca

---

---

## **Docker**

Docker is a platform for developing, shipping, and running applications in containers.

Containers are lightweight, portable, and self-sufficient units that can package an application and its dependencies, including libraries and configuration files, into a single, consistent environment.

This allows developers to create, deploy, and manage applications more efficiently, regardless of the underlying infrastructure.

---

## Let's get down to business

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="center")

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Open a Terminal

---

## **Update packages info**

```plaintext
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install dependencies

```plaintext
sudo apt-get install ca-certificates curl gnupg
```

---

## Set up a directory for keyrings

```plaintext
sudo install -m 0755 -d /etc/apt/keyrings
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702093791048/dd6afbfa-10ec-44d4-ba9f-6e355ad18a0b.png align="center")

The command you provided is creating a directory with specific permissions for apt keyrings.

Keyrings are used in package management systems, like APT (Advanced Package Tool) in Debian-based systems, to manage cryptographic keys for package verification.

---

## Download Docker GPG

```plaintext
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702093783072/9015f0d9-c10c-4c2d-a44e-91188d3d6ce5.png align="center")

  
The command you've provided is using `curl` to download the Docker GPG (GNU Privacy Guard) key from the specified URL and then using `gpg` to convert it into a format suitable for APT package management

---

## Change permissions

```plaintext
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702093780080/8693da94-0b1c-4b6e-a0f8-1946d930518f.png align="center")

---

## Add the repository

```plaintext
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702094965674/6c629c9e-cbc7-4054-b154-d9a18a8fe0b9.png align="center")

---

## Install the Docker packages

```plaintext
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702095098354/d058a6ae-1652-4c54-bace-6e17ab3b180e.png align="center")

---

## Confirm installation

```plaintext
docker --version
which docker
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702095203637/d1179002-546e-4fee-8ca3-f13d602d4471.png align="center")

---

## Run Docker

Let's verify that the Docker Engine installation is successful by running the `hello-world` image.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702095345893/2348d829-e9c6-494c-b7bc-88f7243260e1.png align="center")

---

## Done

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="center")

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
