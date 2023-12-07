---
title: "Installing Node.js with NVM on Pop!_OS 22.04"
datePublished: Thu Dec 07 2023 14:57:17 GMT+0000 (Coordinated Universal Time)
cuid: clpvbnoy0000108l77ncpft02
slug: installing-nodejs-with-nvm-on-popos-2204
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/WJ09YGBdrZs/upload/bfcb9fe07b103c6cc8c36e4aa1267831.jpeg
tags: tutorial, software-development, nodejs, popos, alexandrecalaca

---

---

## **Node JS**

Node.js is an open-source, cross-platform JavaScript runtime environment that allows developers to execute JavaScript code outside of a web browser.

It is designed for building scalable and high-performance network applications, making it particularly well-suited for building server-side applications and APIs (Application Programming Interfaces).

---

## NVM

NVM is used for managing multiple versions of Node.js on a single machine. It enables developers to switch between different Node.js versions based on project requirements.

NVM is particularly useful when you work on multiple Node.js projects that have specific version dependencies. It ensures that each project can use the appropriate Node.js version without interfering with others.

---

## **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

### **Check your OS**

This step is just to make sure you have `Pop!_OS` installed.

```plaintext
uname -a
hostnamectl
lsb_release -a
cat /etc/os-release
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png align="center")

---

## Open a Terminal

---

## Update repository

```plaintext
sudo apt-get update
```

---

## Install dependencies

```plaintext
sudo apt install build-essential libssl-dev
```

---

## **Check the latest NVM versions**

Go to the **releases** page and write down the last version.

At the moment, the link is:

```plaintext
https://github.com/nvm-sh/nvm/releases
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960811559/f90f78af-f531-4f28-bb26-9911f921230b.png align="center")

---

## Install NVM

```plaintext
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```

Replace `v0.39.5` with the chosen version.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960170437/e2341b35-b59b-434e-a9e5-9be5384b91da.png align="center")

`curl` is the command-line tool for making HTTP requests.

It can be used to download files, make API requests, and perform various other HTTP-related tasks.

`-o` is a flag that is used to specify the output file for the downloaded content. By default, curl will save the downloaded content to a file with a name derived from the URL.

When you use `-o` followed by a filename, it tells curl to save the content to that specific file.

The catch is that when you use `-o-` (with a hyphen after it), it instructs curl to send the output to stdout instead of saving it to a file.

---

## **Apply bash changes**

```plaintext
source ~/.bashrc
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960292155/b79401cd-cd6d-43f1-81c9-cae439f4fd3d.png align="center")

The command `source ~/.bashrc` is used to execute the content of the `.bashrc` file in the current shell session.

It is commonly used in Unix-like operating systems, including Linux, to apply changes made to the configuration file without the need to log out or start a new terminal session.

When you run `source ~/.bashrc`, you are telling your current shell session to read and execute the commands in your `.bashrc` file.

his is often done to apply changes to environment variables, aliases, functions, or other shell settings that you've modified or added to your .bashrc file.

---

## Check NVM installation

```plaintext
nvm --version
nvm
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960340747/26a66130-9a08-4b84-a7ad-1e0c11961116.png align="center")

---

## List available versions

```plaintext
nvm ls-remote
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696732894101/b0899799-d855-4e90-aa35-94d3cda42a08.png?auto=compress,format&format=webp align="left")

---

## Install Node.js

```plaintext
nvm install v18.18.0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960414517/89d00f90-5e5e-497e-81ee-b61f9e5c7e66.png align="center")

---

## List local Node.js versions

```plaintext
nvm ls
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960604402/b5aefcb1-46b2-4ec6-b822-943c6566be8a.png align="center")

---

## Set a default version

```plaintext
nvm alias default v18.18.0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960590760/02e7bfb9-b58d-4b9d-a832-3444695437b4.png align="center")

---

## Check Node.js default version

```plaintext
nvm current
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960593038/b1d9049c-346e-4449-b0d3-3a18857d4112.png align="center")

---

## **Done**

---

## Celebrate

![Happy Season 2 GIF by The Office - Find & Share on GIPHY](https://media2.giphy.com/media/jQediRqu0oLXNdjDbN/giphy.gif?cid=6c09b952sfrdnl666a3hp1aeryp278rp59g3w8aj33myfbux&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g align="left")

---

## **Let's become friends**

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