---
title: "How to install Mozilla Firefox on Deepin OS 20.9 or any other Debian-based Linux distribution using the terminal emulator?"
datePublished: Thu Sep 21 2023 02:04:23 GMT+0000 (Coordinated Universal Time)
cuid: clmsj556q000009jkd18pd9gi
slug: how-to-install-mozilla-firefox-on-deepin-os-209-or-any-other-debian-based-linux-distribution-using-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ut3AqIHbPkY/upload/6e3212e59760d372365eba6d878b59d9.jpeg
tags: tutorial, ubuntu, linux, deepin

---

---

## Mozilla Firefox

Mozilla Firefox, commonly referred to as just Firefox, is a free and open-source web browser developed by the Mozilla Corporation.

It is one of the most popular web browsers worldwide and is available for various operating systems, including Windows, macOS, Linux, and mobile platforms.

---

![Suits-2x08 GIFs - Get the best GIF on GIPHY](https://media0.giphy.com/media/3o85xp2sR7StloVo9q/giphy.gif align="center")

---

## Check your OS

```ruby
lsb_release -a
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695259933225/14f1c0da-f529-49fe-a022-c71d1acda573.png align="center")

---

## Go to the download page

In your browser's address bar:

```plaintext
https://www.mozilla.org/en-US/firefox/download/thanks/
```

---

## Go to the folder

In your terminal emulator, go the folder where the firefox file has been saved.

```plaintext
cd ~/Downloads
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695260431293/9f156dff-75ae-4cc0-ba68-124f8ec40a19.png align="center")

`~` is called the tilde character, it represents the user's home directory.

In most Unix-like systems, each user has a home directory where their personal files and settings are stored. The `~` symbol is a shortcut for the home directory of the currently logged-in user.

---

## Extract the content

Extract the content of the downloaded firefox executable file:

```apache
tar xjf firefox-117.0.1.tar.bz2 firefox/
```

`tar`: This is the command for working with tar archives in Unix-like operating systems.

`x`: This option stands for "extract." It tells the `tar` command to extract the contents of an archive.

`j`: This option specifies that the archive is compressed using the bzip2 compression format. In this case, "firefox-117.0.1.tar.bz2" is a bzip2-compressed tarball.

`f`: This option is used to specify the archive file to be operated on. It must be followed by the name of the archive file, which in this case is "firefox-117.0.1.tar.bz2."

`firefox/`: This is the target directory where the contents of the archive will be extracted. In this case, it's a directory named "firefox."

---

## Move the folder

```apache
sudo mv firefox /opt
```

`/opt/` is a directory in the root file system that is often used for installing and storing software packages that are not part of the core operating system. It's a common location for third-party or manually installed software.

So, when you run `sudo mv firefox /opt/`, you are moving the "firefox" directory from its current location to the "/opt/" directory.

This is often done when we want to install Firefox manually or manage its installation yourself, as it allows you to place Firefox in a system-wide location where it can be easily accessed by multiple users on the system.

---

## Create a symbolic link

A symlink, short for symbolic link, is a special type of file in a Unix-like or Linux operating system that acts as a pointer or reference to another file or directory.

Symlinks are also sometimes referred to as `soft links` or symbolic links. They are commonly used for various purposes in system administration, file management, and software development.

```apache
sudo ln -s /opt/firefox/firefox /usr/local/bin/firefox
```

---

## Download the desktop file

```apache
sudo wget https://raw.githubusercontent.com/mozilla/sumo-kb/main/install-firefox-linux/firefox.desktop -P /usr/local/share/applications
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695261304308/560ae7e8-452e-4632-812c-59e59c6cd4d7.png align="center")

So, when we run this command, it downloads the Firefox desktop file from the specified URL and saves it in the `/usr/local/share/applications` directory.

This allows your desktop environment (such as GNOME, KDE, or others) to recognize Firefox as an installed application and make it accessible through your system's application launcher.

After running this command and assuming Firefox is correctly installed on our system, we should be able to find and launch Firefox from our application menu or launcher like any other installed application.

---

## Check installation

### Through the executable file's path

In your terminal emulator:

```plaintext
which firefox
```

Output

```ruby
elitebughunter@elitebughunter-deepin-os:~/Downloads$ which firefox
/usr/local/bin/firefox
```

---

### Through its version

```ruby
firefox -v
```

Output

```apache
elitebughunter@elitebughunter-deepin-os:~/Downloads$ firefox -v
Mozilla Firefox 117.0.1
```

---

### Through its post-installation run

```ruby
firefox
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695261560427/f4f9c998-bd9a-4673-a644-a6135a32b8fd.png align="center")

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