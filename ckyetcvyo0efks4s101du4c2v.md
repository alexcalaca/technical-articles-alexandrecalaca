---
title: "How to check the version of Ubuntu or any other Linux distribution using the command line?"
datePublished: Fri Jan 14 2022 19:48:37 GMT+0000 (Coordinated Universal Time)
cuid: ckyetcvyo0efks4s101du4c2v
slug: how-to-check-the-version-of-ubuntu-or-any-other-linux-distribution-using-the-command-line
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642092552050/SKAzGwmDN.png
tags: ubuntu, linux

---

Hey guys, what's up?

### Introduction
The goal of this article is to check the version of Ubuntu or any other Linux distribution using the command line.

### The "magic" command
The "magic" command is `lsb_release`.

#### Introduction
The most reliable command is `lsb_release`. `lsb` stands for Linux Standard Base and it  displays information about a specific Linux distribution.

It's a simple and reliable tool to help to identify the Linux distribution being used.

There are other commands, however this one works on all Linux distributions.

#### Syntax
```
lsb_release [options]
```
#### The options
In order to know all the available options, type the following code in the terminal:
```
lsb_release -h

```
You'll get something like this:
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1642091442318/jGY4FBBLe.png)

In case you want to copy it:

```
Options:
  -h, --help         show this help message and exit
  -v, --version      show LSB modules this system supports
  -i, --id           show distributor ID
  -d, --description  show description of this distribution
  -r, --release      show release number of this distribution
  -c, --codename     show code name of this distribution
  -a, --all          show all of the above information
  -s, --short        show requested information in short format
```

The most important options are `-h`, since it allows you to see all the available options, and `-a`, because it's going to show all the available information about the current Linux distribution.

#### Down to business
Open the terminal. Let's check some examples.

```
calaca@alexandre-calaca:~$ lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 20.04.3 LTS
Release:	20.04
Codename:	focal
```
or

```
lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 18.04.5 LTS
Release:    18.04
Codename:   bionic
```


### Conclusion
In this article, it was possible to learn how to check the version of Ubuntu or any other Linux distribution using the command line.

Hope it was useful.

That's for today. 

By the way, you help me a lot if you like and/or share this article.