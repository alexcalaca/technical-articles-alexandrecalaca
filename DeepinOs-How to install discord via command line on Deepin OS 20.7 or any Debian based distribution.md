---
title: "DeepinOs-How to install discord via command line on Deepin OS 20.7 or any Debian based distribution"
datePublished: Sat Apr 29 2023 03:17:28 GMT+0000 (Coordinated Universal Time)
cuid: clh1ewmjk000309lb0ur6d6j1
slug: deepinos-how-to-install-discord-via-command-line-on-deepin-os-207-or-any-debian-based-distribution
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xbEVM6oJ1Fs/upload/1535753840bc9d119a90ad1c73278f69.jpeg
tags: ubuntu, linux, debian

---

#### `Revisited on June 28th, 2023`

---

#### Open the terminal

Press `CTRL + Alt + T` on your keyboard

---

#### Check your OS

In case you don't really know if you're running Ubuntu or any Debian based distro version, you can can the following command in terminal:

```apache
lsb_release -a
```

The output would be something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682732204295/e54d336c-1f5d-4cf6-b7fc-2ff6b8b87cff.png align="center")

---

#### Install management software repository

`sudo apt-get install software-properties-common`

Your output should be something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682732686956/88771717-1b2a-4daa-b1db-b5c801934935.png align="center")

---

#### Update the system

```apache
sudo apt-get update
```

---

#### Install snap

`sudo apt install snapd`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682733558648/bcfbd217-2bc4-46ad-bcc8-1779e1a4408c.png align="center")

---

#### Check if snap is installed

```apache
snap version
```

Your output should be something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682737942791/11ac52ac-5355-401f-9eb6-712898dc2e7f.png align="center")

---

#### Install Discord via snap

```apache
sudo snap install discord
```

Your output would be something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682735601633/4186eeb0-beab-4991-bf9c-a5329c14af6f.png align="center")

---

#### Check if Discord is installed

```apache
snap list discord
```

Your output should be something like the following

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682737985919/e65130d0-9f31-48c5-9bd7-e40006ba94dc.png align="center")

---

#### Celebrate

![Pleasantly Surprised GIF - Michael Scott Steve Carell OMG - Discover &  Share GIFs](https://media.tenor.com/teFSAfy_xVQAAAAC/michael-scott-steve-carell.gif align="left")

---
