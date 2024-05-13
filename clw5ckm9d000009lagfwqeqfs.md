---
title: "Installing the best terminal emulator on Pop!_OS 22.04: Terminator"
datePublished: Mon May 13 2024 19:18:49 GMT+0000 (Coordinated Universal Time)
cuid: clw5ckm9d000009lagfwqeqfs
slug: installing-the-best-terminal-emulator-on-popos-2204-terminator
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715627913483/31afb33c-175b-46ea-8768-88cdb9d9d898.avif
tags: ubuntu, popos, alexandrecalaca

---

## **Terminator**

![GNOME Terminator - Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Gnome-Terminator.svg/1200px-Gnome-Terminator.svg.png align="left")

Terminator is a popular choice among Linux users, particularly those who work extensively with the command line, because of its advanced features and flexibility.

It's available in the software repositories of many Linux distributions and can be installed using package managers like APT (for Debian/Ubuntu-based systems) or YUM (for Red Hat/Fedora-based systems).

---

## **Let's get down to business**

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="left")

---

### **Check your OS (optional)**

This step is just to make sure you have `Pop!_OS` installed.

**COPY**

**COPY**

**COPY**

```ruby
uname -a
hostnamectl
lsb_release -a
cat /etc/os-release
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## **Update packages info**

**COPY**

**COPY**

**COPY**

```ruby
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install Terminator

**COPY**

**COPY**

**COPY**

```ruby
sudo apt install terminator
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702148600936/5e72dd95-4856-4423-a86e-456b9a538737.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Check installation

**COPY**

**COPY**

**COPY**

```ruby
terminatlr --version
which terminator
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702148745629/e87cd0cc-e945-4a93-901f-2b2bf4c43223.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Run

**COPY**

**COPY**

**COPY**

```ruby
terminator
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702148855419/cf190759-a47d-4766-85e0-ba3675118ac9.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## **Done**

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

## **Reach me out**

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