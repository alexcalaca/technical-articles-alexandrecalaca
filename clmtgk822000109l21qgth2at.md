---
title: "How to install Visual Studio Code on Linux Mint 21 vanessa or any other Ubuntu-based Linux distribution with a Debian file format"
datePublished: Thu Sep 21 2023 17:39:53 GMT+0000 (Coordinated Universal Time)
cuid: clmtgk822000109l21qgth2at
slug: how-to-install-visual-studio-code-on-linux-mint-21-vanessa-or-any-other-ubuntu-based-linux-distribution-with-a-debian-file-format
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695317878036/d1448a1a-41c9-432c-bd13-49ccd4934ca3.webp
tags: tutorial, ubuntu, vscode, linux-mint, installation

---

---

## Go to the site

```ruby
https://code.visualstudio.com/docs/setup/linux
```

---

## Download

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695316528893/6ee406d0-404f-425a-aba4-660e4f6be37d.png align="center")

---

## Choose .deb

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695316576661/002d37bb-8341-4f50-9c00-c590952fff66.png align="center")

---

## Install VS Code

```ruby
sudo apt install gdebi
```

Using `gdebi` is a convenient way to handle `.deb` file installations because it automatically resolves dependencies and ensures that the package is properly integrated with your system.

---

## Install

```ruby
sudo gdebi ~/Downloads/code_1.82.2-1694671812_amd64.deb 
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695316867846/99637edb-5a5f-496e-9a2e-75ccb9903ef4.png align="center")

---

## Check installation

### Through version

```ruby
code --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695317047134/b66b7c70-83cc-4604-94ea-58104ae0810d.png align="center")

---

### Through the executable file's path

```ruby
which code
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695317047134/b66b7c70-83cc-4604-94ea-58104ae0810d.png align="center")

---

### Through post-installation run

```ruby
code &
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695317047134/b66b7c70-83cc-4604-94ea-58104ae0810d.png align="center")

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