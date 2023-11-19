---
title: "Set up the GitHub command line interface (CLI) tool on Linux Mint 21 vanessa"
datePublished: Sun Nov 19 2023 02:43:45 GMT+0000 (Coordinated Universal Time)
cuid: clp4vj1qc000208ld1y4b9t9x
slug: set-up-the-github-command-line-interface-cli-tool-on-linux-mint-21-vanessa
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700361742049/a962744f-90c6-40b2-8ea6-1003626133a2.png
tags: linux, github, git, linux-for-beginners, alexandrecalaca

---

---

## Github CLI

The GitHub Command Line Interface (CLI) tool, often referred to as `gh`, is a command-line tool provided by GitHub for interacting with GitHub repositories and performing various GitHub-related actions directly from the command line.

With the GitHub CLI, you can perform tasks such as creating repositories, managing issues and pull requests, viewing repository information, and more, all without having to use a web browser.

The GitHub CLI is designed to streamline workflows for developers who prefer working in a terminal environment.

---

### **Let's get down to business**

shall we?

![Harvey Specter Suits GIF - Harvey Specter Suits Fixa Gr Det - Discover &  Share GIFs](https://media.tenor.com/dF3PRUrNCHUAAAAC/harvey-specter-suits.gif align="center")

---

## Solution

---

## **Check your OS**

This step is just to make sure you have **Linux Mint** or a **Ubuntu-**based Linux distribution.

```plaintext
cat /etc/os-release
lsb_release -a
uname -a
hostnamectl
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696187393881/b9d11c02-f4db-4f41-bce5-fd13d690c4c1.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Open the terminal

You can open a terminal by pressing Ctrl + Alt + T or by searching for "Terminal" in the application [menu.](http://menu.ls)

---

### Add a GPG key to the system's keyring

```plaintext
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key C99B11DEB97541F0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700359526677/7ba9a70a-e947-4f51-b68d-0d3dca7c8f04.png align="center")

---

### **Brief explanation**

The `apt-key` command is used for managing authentication keys used to authenticate packages.

`adv`: This stands for "advanced."  
  
`--keyserver` [`keyserver.ubuntu.com`](http://keyserver.ubuntu.com): This specifies the key server from which to receive the GPG key. In this case, it's the Ubuntu key server.

`--recv-key C99B11DEB97541F0`: This specifies the GPG key's identifier that should be retrieved from the key server. The GPG key is a cryptographic key used to sign packages, and this command fetches and adds that key to the system's keyring.

---

## Add a new repository

```plaintext
sudo apt-add-repository https://cli.github.com/packages
```

---

## Install

```plaintext
sudo apt-get install gh
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700360003444/82f0fb02-6e07-4ff5-98cd-33cfb82c30ff.png align="center")

---

## Verify installation

```plaintext
gh --version
which gh
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700360169829/77d825f0-b64b-4747-9516-417d8aa7ba22.png align="center")

---

## Initiate authentication process

Before using `gh`, you need to authenticate with your GitHub account. Run the following command and follow the prompts:

```
gh auth login
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700360266760/6319d3f7-86d4-4325-b1e5-b20b0bcba2a0.png align="center")

---

### Choose preferred protocol

I picked up `SSH`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700361385818/91d18009-05a7-4469-aa40-c98455d40642.png align="center")

---

### Upload the SSH public key

I picked up my current SSH public key.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700361414613/ce5a5b29-98c7-4e76-bf9b-840eda5e8f62.png align="center")

---

### Authenticate

I used the \`authentication token \`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700361435352/84e38a77-ca83-4edd-b767-eeaee29afa69.png align="center")

---

### Check

You can check if you are really logged in by trying to authenticate again.

```plaintext
gh auth login
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700361517016/ce7190f7-bc55-44b9-a827-b7899dc798f8.png align="center")

---

## Done

---

## Celebrate

Well-done. You did a great job!

![Casts Of The Office Celebration Dance GIF | GIFDB.com](https://gifdb.com/images/high/casts-of-the-office-celebration-dance-p9rrkj7pyawhjo54.gif align="left")

---

## **Let's connect**

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