---
title: "Installing Node.js with NVM on Linux Mint 21 vanessa or Ubuntu-based Distros"
datePublished: Sun Oct 01 2023 02:36:47 GMT+0000 (Coordinated Universal Time)
cuid: cln6upccd000008mwgzhif5uv
slug: installing-nodejs-with-nvm-on-linux-mint-21-vanessa-or-ubuntu-based-distros
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ZS67i1HLllo/upload/47a05e887ec1c266bbdce469d6e5f86f.jpeg
tags: programming-blogs, linux, javascript, nodejs, nvm

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

This step is just to make sure you have **Linux Mint** or a **Ubuntu-**based Linux distribution.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695496363425/6f056578-4c7a-4b87-929d-106b8c01f28a.png?auto=compress,format&format=webp align="left")

---

## Open a Terminal

Open a terminal window on your Linux Mint 21 system. You can typically do this by pressing `Ctrl + Alt + T` or searching for "Terminal" in the application launcher.

```ruby
Ctrl + Alt + T
```

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696126148218/94bc60e4-82f9-4e4a-8bdd-7bd215b4252f.png align="center")

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

The command `source ~/.bashrc` is used to execute the content of the `.bashrc` file in the current shell session. It is commonly used in Unix-like operating systems, including Linux, to apply changes made to the configuration file without the need to log out or start a new terminal session.

When you run `source ~/.bashrc`, you are telling your current shell session to read and execute the commands in your `.bashrc` file. This is often done to apply changes to environment variables, aliases, functions, or other shell settings that you've modified or added to your .bashrc file.

---

## Check NVM installation

```ruby
nvm --version
nvm
```

output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696127009177/e7b37e8c-c555-4ef5-9c37-db2db5820754.png align="center")

---

## List available versions

```ruby
nvm ls-remote
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696127189115/3ff3a0c5-f669-41ae-8c20-94fbd4f547e2.png align="center")

---

## Install Node.js

```ruby
nvm install v18.18.0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696127257309/763bb911-3c5c-45c3-8e39-74b6b861110a.png align="center")

---

## List local Node.js versions

```ruby
nvm ls
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696127323718/85c62ce0-6dc7-40e0-9a8e-918a0246fe57.png align="center")

---

## Set a default version

```ruby
nvm alias default v18.18.0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696127493810/7a7d188f-0b9f-40ea-824c-e1d84312d05f.png align="center")

---

## Check Node.js default version

```ruby
nvm current
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696127554959/99ace6c3-a74e-4971-9f9e-9a5500b41dd4.png align="center")

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