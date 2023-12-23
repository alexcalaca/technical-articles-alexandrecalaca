---
title: "RVM: How to install RVM  on Deepin Linux OS 20.7"
datePublished: Thu Dec 08 2022 02:44:40 GMT+0000 (Coordinated Universal Time)
cuid: clbeh7h2q000008l6gj06aikj
slug: rvm-how-to-install-rvm-on-deepin-linux-os-207
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699041099981/fdd0ced2-7f04-4f2a-a8a4-fc6d54603d83.png
tags: linux, ruby, debian, deepin, deepinos

---

`Revisited and updated on November 03rd, 2023`

---

Hey guys, how have you been?

Today, we are going to learn how to install `RVM` on Deepin OS 20.7, a Debian-based distro.  
Actually, this procedure can be done in any Debian based distro.

---

### Introduction

`RVM` is a command-line tool that allows you to easily install, manage, and work with multiple ruby environments from interpreters to sets of gems. It was originally started in October of 2007.

Ruby Version Manager, often abbreviated as RVM, is a software platform for Unix-like operating systems designed to manage multiple installations of Ruby on the same device.

---

## Update your system

Open the terminal and run the following command:

```plaintext
sudo apt update
```

---

## Install the required dependencies

```plaintext
sudo apt install apt-transport-https ca-certificates gnupg2 curl
```

---

## Import GPG Key

GPG stands for Gnu Privacy Guard and it is supported by the Internet Engineering Task Force ([IETF](https://www.ietf.org/)) through the [RFC 4880](https://www.ietf.org/rfc/rfc4880.txt).

The IETF publishes RFCs authored by network operators, engineers, and computer scientists to document methods, behaviors, research, or innovations applicable to the Internet.

GnuPG (more commonly known as GPG) is an implementation of a standard known as PGP (Pretty Good Privacy). It uses a system of "public" and "private" keys for the encryption and signing of messages or data.

```plaintext
curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -
```

---

## Install the RVM stable version

```plaintext
curl -sSL https://get.rvm.io | bash -s stable --ruby
```

By now, you should be able to see something like this:

![Screenshot_select-area_20221207231910.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670466689550/hvlEa0DXD.png align="left")

---

## Start using RVM

```plaintext
source /home/elitebughunter/.rvm/scripts/rvm
```

---

## Check RVM installation

```plaintext
rvm -v
which rvm
```

You should be able to see something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699040808210/6dac4e92-9eb6-4308-a722-d165925c6bcd.png align="center")

---

## List all Ruby versions available

```plaintext
rvm list known
```

You should be able to see something like this:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670467136561/oePiQQOwU.png align="left")

---

## Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670467202120/39r84GZVW.png align="left")

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

---

### **Final thoughts**

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---
