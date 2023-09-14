---
title: "How to solve the Error "bash: git: command not found" on Deepin OS 20.7 or any other Debian-based Linux distribution?"
datePublished: Thu Sep 14 2023 14:11:01 GMT+0000 (Coordinated Universal Time)
cuid: clmj90n22000g08if7cltfn4e
slug: how-to-solve-the-error-bash-git-command-not-found-on-deepin-os-207-or-any-other-debian-based-linux-distribution
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/npxXWgQ33ZQ/upload/45a842dc44eb0728ae839a3d16306490.jpeg
tags: tutorial, ubuntu, linux, git, debian

---

---

## Git

Git is a distributed version control system (DVCS) used for tracking changes in source code during software development.

It is a powerful and widely used tool in the field of software development and is essential for managing and collaborating on code with multiple team members.

Git is commonly used in conjunction with online platforms like GitLab, GitHub, and Bitbucket, which provide additional collaboration features, issue tracking, continuous integration, and more.

---

## Error

```plaintext
bash: git: command not found
```

Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694699566906/b78cf5c7-6c11-49db-af32-c23059fdcf64.png align="center")

---

## Brief explanation

The error message "bash: git: command not found" indicates that Git is not installed on your system.

---

## Check installation

Let's check if `git` is installed.

---

### Through the version

```plaintext
git --version
```

This should display the installed Git version, confirming that Git is now available on your system. if you don't see, it's because Git is not installed on your system.

---

### Locate the executable path

The `which` command in Linux is used to locate and display the path to an executable file associated with a given command.

It helps you determine the location of the executable that would be run if you were to execute a particular command in your shell.

```plaintext
which git
```

if there's no output, it's because Git is not installed on your system.

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694700029378/a81148f2-10cd-4fcc-ac21-b7f9d975c98b.png align="center")

---

### Through the executable path

```plaintext
which git
```

This should display the installed Git version.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694700089957/218c96e9-4ef3-487b-ad6c-e136bd10fadf.png align="center")

---