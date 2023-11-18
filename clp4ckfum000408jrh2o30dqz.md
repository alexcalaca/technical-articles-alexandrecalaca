---
title: "Install and configure a default Node.JS version with NVM on Linux Mint 21 vanessa"
datePublished: Sat Nov 18 2023 17:52:58 GMT+0000 (Coordinated Universal Time)
cuid: clp4ckfum000408jrh2o30dqz
slug: install-and-configure-a-default-nodejs-version-with-nvm-on-linux-mint-21-vanessa
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/4hbJ-eymZ1o/upload/f029d7ded44ee970537ae3528d0e1c52.jpeg
tags: tutorial, linux, nodejs, linux-basics, alexandrecalaca

---

---

## Node JS

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

### Check your OS

This step is just to make sure you have **Linux Mint** or a \*\*Ubuntu\*\* based Linux distribution.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
hostnamectl
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696732362459/4c2bd868-1572-49d4-8cf2-5620950290cc.png align="center")

---

## Open a Terminal

Open a terminal window on your `Linux Mint 21 vanessa`. You can typically do this by pressing `Ctrl + Alt + T` or by searching for "Terminal" in the application launcher.

```ruby
Ctrl + Alt + T
```

---

## Update repository

```apache
sudo apt-get update
```

---

## Install dependencies

```apache
sudo apt install build-essential libssl-dev -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700328733537/96db4c3c-66d5-4c24-83da-762f5f3fac83.png align="center")

---

## Check the latest NVM versions

Go to the **releases** page and write down the last version.

At the moment, the link is:

```ruby
https://github.com/nvm-sh/nvm/releases
```

---

## Install NVM

```ruby
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```

Replace `v0.39.5` with the chosen version.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700329397112/f6d9c870-1fb0-4c7d-aa17-4e194a1af532.png align="center")

`curl` is the command-line tool for making HTTP requests.

It can be used to download files, make API requests, and perform various other HTTP-related tasks.

`-o` is a flag that is used to specify the output file for the downloaded content. By default, curl will save the downloaded content to a file with a name derived from the URL.

When you use `-o` followed by a filename, it tells curl to save the content to that specific file.

The catch is that when you use `-o-` (with a hyphen after it), it instructs curl to send the output to stdout instead of saving it to a file.

---

## Apply bash changes

```ruby
source ~/.bashrc
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696732772341/f5eb7b34-b4b2-4f97-8507-6bfbab799145.png align="center")

The command `source ~/.bashrc` is used to execute the content of the `.bashrc` file in the current shell session. It is commonly used in Unix-like operating systems, including Linux, to apply changes made to the configuration file without the need to log out or start a new terminal session.

When you run `source ~/.bashrc`, you are telling your current shell session to read and execute the commands in your `.bashrc` file. This is often done to apply changes to environment variables, aliases, functions, or other shell settings that you've modified or added to your .bashrc file.

---

## Check NVM installation

```ruby
nvm --version
nvm
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696732836729/b52a1adb-1bec-4ddc-8d96-8934efbe0a9b.png align="center")

---

## List available versions

```ruby
nvm ls-remote
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696732894101/b0899799-d855-4e90-aa35-94d3cda42a08.png align="center")

---

## Install Node.js

```ruby
nvm install v18.18.0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700329557325/81868d68-3560-4168-b756-e20bb35dc401.png align="center")

---

## List local Node.js versions

```ruby
nvm ls
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700329615685/8a3058d4-fa97-4daf-ad1b-c8c22de68cff.png align="center")

---

## Set a default version

```ruby
nvm alias default v18.18.0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700329779271/fdac2aa4-eb4a-49be-acdf-97f602bfc27e.png align="center")

---

## Check Node.js default version

```ruby
nvm current
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700329767656/f8a395b7-fdcd-4c36-8d11-ebb58d85dca4.png align="center")

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