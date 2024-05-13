---
title: "How to install Git on Linux Mint 21 vanessa"
datePublished: Mon May 13 2024 19:17:30 GMT+0000 (Coordinated Universal Time)
cuid: clw5cixpo00010ajqgq5kdf7r
slug: how-to-install-git-on-linux-mint-21-vanessa
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/UT8LMo-wlyk/upload/81922d494f8e2171be5d179b8f9eb5eb.jpeg
tags: linux, github, alexandrecalaca

---

---

## **Git**

Git is a distributed version control system (DVCS) used for tracking changes in source code during software development.

It is a powerful and widely used tool in the field of software development and is essential for managing and collaborating on code with multiple team members.

Git is commonly used in conjunction with online platforms like GitLab, GitHub, and Bitbucket, which provide additional collaboration features, issue tracking, continuous integration, and more.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

## **Check your OS**

This step is just to make sure you have **Linux Mint** or a \*\*Ubuntu-\*\*based Linux distribution.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
hostnamectl
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696187393881/b9d11c02-f4db-4f41-bce5-fd13d690c4c1.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694699566906/b78cf5c7-6c11-49db-af32-c23059fdcf64.png align="center")

---

## Update the package manager

```plaintext
sudo apt-get update
```

---

## Install Git

```plaintext
sudo apt-get install git -y
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694699948834/e5f6de29-f6fc-4408-b235-8859280915d3.png align="center")

---

## Check installation

### Through the version

```plaintext
git --version
```

This should display the installed Git version.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700331761787/c02ed31d-8aa5-4589-bfc7-58aa72a1c01a.png align="center")

---

### Through the executable path

```plaintext
which git
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700331774703/bdd3d7b9-6fad-4d86-80c7-f28d766ab0ba.png align="center")

---

## **Done**

---

## Celebrate

Well-done. You did a great job!

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

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