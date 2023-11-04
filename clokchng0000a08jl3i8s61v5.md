---
title: "Resolving Docker 'Credential Store Not Initialized' Error on Deepin Linux OS 20.9"
datePublished: Sat Nov 04 2023 17:55:24 GMT+0000 (Coordinated Universal Time)
cuid: clokchng0000a08jl3i8s61v5
slug: resolving-docker-credential-store-not-initialized-error-on-deepin-linux-os-209
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699120279634/8fe6ca48-689d-46bc-97de-fc85f3a14260.png
tags: software-development, programming-blogs, linux, docker, deepin

---

---

## **Situation**

```plaintext
Credential store not initialised
Docker Desktop uses 'pass' to store the login credentials that needs to be initialised.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699117999488/ecc787a4-3358-4f1e-9da8-05683f6724eb.png align="center")

---

## **Credential store not initialised**

Docker Desktop is a desktop application that provides an integrated development environment for Docker.

The error message we're seeing, `credential store not initialised` is related to Docker's credential store, which is used to securely store and manage login credentials for Docker registries.

Docker uses different credential helpers or credential stores on different platforms, and on Linux, it often uses `pass` as one of the credential helpers.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

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

## Check Docker installation (optional)

Make sure your Docker is up and running [here](https://blog.alexandrecalaca.com/how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator) or through the following link:

[https://blog.alexandrecalaca.com/how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator](https://blog.alexandrecalaca.com/how-to-set-up-docker-on-deepin-linux-os-209-via-the-terminal-emulator)

---

## Check Docker desktop installation (optional)

Make sure your Docker desktop is up and running [here](https://blog.alexandrecalaca.com/how-to-configure-docker-desktop-on-deepin-linux-os-209) or through the following link: [https://blog.alexandrecalaca.com/how-to-configure-docker-desktop-on-deepin-linux-os-209](https://blog.alexandrecalaca.com/how-to-configure-docker-desktop-on-deepin-linux-os-209)

---

## Generate a gpg key

```plaintext
gpg --generate-key
```

The `gpg --generate-key` command is used to generate a new GPG (GNU Privacy Guard) key pair.

GPG is a widely used open-source software for encrypting and signing data and is commonly used for securing email communications, verifying the authenticity of software packages, and protecting sensitive information.

---

## Provide information

Provide real name and email address

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699118803035/f5e2c0fb-5f1b-49e6-bf00-7be233615f70.png align="center")

---

## Choose a passphrase

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699118637833/948b1caa-80de-4474-8456-2646fd0d4862.png align="center")

---

## Visualize your gpg key

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699118934427/1e58cbcd-4ce4-4d37-95c1-abeb828d4775.png align="center")

---

## List the keys

The following lists all the public keys

```plaintext
gpg --list-keys
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119146466/25700c0f-df68-48d6-843c-cea10dc53b37.png align="center")

Just in case you want to list all your private keys, you should run the following command:  
gpg --list-secret-keys

---

## Copy your public key

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119262142/5f45871a-d084-4ab4-8517-7ca24aaa49cf.png align="center")

---

## Initialize pass

```plaintext
pass init your-key
```

It should be something like the following:

```plaintext
pass init DAZF877093FCF03Z4BFA3A0456CD93F8BCFC51B4
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119385460/0ce003b2-a9da-4abe-afcd-73bcc04800ea.png align="center")

---

## Open Docker desktop

Click on sign-in

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119829149/0a21a8a7-b479-4135-8542-4ea87ba58eb4.png align="center")

---

## Login

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119888743/1b0d5f5f-8ccc-4c39-8041-d7bebfa7e814.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119936035/d7375a7b-3677-4590-947b-bc816fab92fa.png align="center")

---

## Proceed to Docker desktop

Click on `Open xdg-open`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119997786/f7700bfc-1aab-4c4e-b456-3a972d00200e.png align="center")

---

## Logged in

Now, you should see your logged in.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699120067583/a9017574-2012-4e79-b74d-884fe67049e9.png align="center")

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

---