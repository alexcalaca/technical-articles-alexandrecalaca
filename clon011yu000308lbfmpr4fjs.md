---
title: "How to install Discord manually on Fedora 38 with good Linux practices"
datePublished: Mon Nov 06 2023 14:29:53 GMT+0000 (Coordinated Universal Time)
cuid: clon011yu000308lbfmpr4fjs
slug: how-to-install-discord-manually-on-fedora-38-with-good-linux-practices
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/sIFCJHrUWPM/upload/dd82c84c7b254209071e26c1dee437c3.jpeg
tags: linux, fedora, alexandrecalaca

---

---

## Discord

Discord is a popular communication platform that primarily focuses on enabling text, voice, and video communication.

It was initially created for gamers to communicate with each other while playing online games, but it has since grown to become a widely used communication tool for various communities and purposes.Check your OS

This step is optional. It's just to make sure you have `Fedora`installed.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

## **Check your OS (optional)**

This step is just to ensure you have **Fedora 38 Linux installed. You can pick up one command or you can use them all.**

### /etc/os-release

```ruby
cat /etc/os-release
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910445814/c08acc61-4276-4d0c-885a-27e3c1a07536.png?auto=compress,format&format=webp align="left")

---

### hostnamectl

```ruby
hostnamectl
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910683442/f37384f0-4274-498a-8130-82c4d90d01aa.png?auto=compress,format&format=webp align="left")

When you run `hostnamectl` without any options, it provides detailed information about the system's hostname, operating system, kernel, and other system-related settings.

---

## lsb\_release

```ruby
lsb_release -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910719446/6460fa24-aa93-4c5c-9101-d45a5b382fe8.png?auto=compress,format&format=webp align="left")

`lsb_release` is a command-line utility commonly found in Linux distributions that adhere to the Linux Standard Base (LSB). The LSB is a standardization initiative that aims to increase compatibility between different Linux distributions by defining a common set of libraries and conventions.

---

### uname

```ruby
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910869580/e24b0907-cf0f-4a3f-924e-021fb67670a4.png?auto=compress,format&format=webp align="left")

The `uname -a` command is used to display detailed system information about the Linux operating system. It provides information about the system's kernel and other system-related details.

---

## **Navigate to the official page**

Go to the following link and click on `Download`

```ruby
https://discord.com/download
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698772991491/495d1112-083f-46ca-ae1f-94b7ee1dc9fd.png?auto=compress,format&format=webp align="left")

---

## Download the tar.gz package

---

## Extract the file

```ruby
sudo tar -xzvf ~/Downloads/discord-0.0.33.tar.gz -C /opt/
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699279365596/ce35e16c-9073-48d4-aa8c-fb9305aab968.png align="center")

---

## Check extracted files

```ruby
ls /opt/Discord/
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699279448646/db1e2612-0fa5-4adf-a19d-d6c557102d07.png align="center")

---

### The /opt/ folder

The `/opt/telegram` is the destination directory where we want to move the "Discord" directory. `/opt` is a common location for installing optional or third-party software on Linux systems.

This is a common method for organizing and installing software on Linux systems. After moving, the software installed in "/opt/Discord" can be run from there, and it may require administrative privileges due to the use of sudo.

---

## Create a Symlink

```ruby
sudo ln -s /opt/Discord/Discord /usr/bin/discord
```

You can create a symbolic link to make launching Discord easier without specifying the full path each time.

---

## Open Desktop application entries

```ruby
cd /usr/share/applications
```

---

## Create Desktop entry

```ruby
sudo nano discord.desktop
```

---

## Add desktop entry

```ruby
[Desktop Entry]
Name=Discord
Comment=All-in-one voice and text chat for gamers
GenericName=Voice Chat
Exec=discord
Terminal=false
Type=Application
Icon=/opt/Discord/discord.png
Categories=Network;
StartupWMClass=discord
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699280315918/dcb005d8-1a02-43f2-bae8-7f0bbc7a7e64.png align="center")

---

## Make Discord executable

```ruby
sudo chmod +x /opt/Discord/Discord
```

---

## **Update the Desktop Database**

```ruby
sudo update-desktop-database
```

---

## Menu

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699280781008/c1f0c38b-cca5-48aa-9b2e-b474561b4dd9.png align="center")

---

## Open Discord

---

## Done

---

## Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

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

---