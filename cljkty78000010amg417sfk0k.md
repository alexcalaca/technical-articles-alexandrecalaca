---
title: "How to install Discord on Deepin OS 20.7 or any other Debian-based distro"
datePublished: Sun Jul 02 2023 02:45:38 GMT+0000 (Coordinated Universal Time)
cuid: cljkty78000010amg417sfk0k
slug: how-to-install-discord-on-deepin-os-20-7-or-any-other-debian-based-distro
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688265859148/c8cf9298-99f7-47de-b908-b0d3ffc398bf.png
tags: ubuntu, linux, debian, deepin

---

---

## Topic

How to install Discord on Deepin OS 20.7 or any other Debian-based distro

---

## Check your OS

You can try one of the following approaches.

---

### **lsb\_release**

The command "lsb\_release -a" is used to display information about the Linux Standard Base (LSB) and distribution-specific information of your Linux system.

The "lsb\_release" command is useful for identifying the distribution and its version in a standardized manner, particularly if you are writing scripts or need to retrieve distribution information programmatically.

```apache
lsb_release -a
```

The output should be something like this

```apache
No LSB modules are available.
Distributor ID: Deepin
Description:    Deepin 20.7.1
Release:        20.7.1
Codename:       apricot
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687569384827/ae7a581e-9ec9-4fdd-baa5-5254a9f317fc.png?auto=compress,format&format=webp align="left")

---

### **os-release**

The command `cat /etc/os-release` is used to display the contents of the "/etc/os-release" file, which contains information about the operating system distribution.

The "/etc/os-release" file is commonly used by various system utilities and scripts to determine the distribution and retrieve specific information about the operating system.

In the terminal

```apache
cat /etc/os-release
```

Your output should be something like the following:

```apache
PRETTY_NAME="Deepin 20.7.1"
NAME="Deepin"
VERSION_ID="20.7.1"
VERSION="20.7.1"
VERSION_CODENAME="apricot"
ID=Deepin
HOME_URL="https://www.deepin.org/"
BUG_REPORT_URL="https://bbs.deepin.org/"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687569637090/70cc8220-890b-436f-8c08-3a885531a6f6.png?auto=compress,format&format=webp align="left")

---

### **Debian-based distro**

In the terminal

```apache
cat /etc/debian_version
```

Output

```apache
10.10
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687569882413/6bf2ea0e-16d5-4d55-8cce-4ae09077dc13.png?auto=compress,format&format=webp align="left")

---

## Update the system

In the terminal

```apache
sudo apt update
```

When it gets done, go to the following:

```apache
sudo apt upgrade
```

---

## Download Discord

In the terminal:

```apache
wget "https://discord.com/api/download?platform=linux&format=deb" -O discord.deb
```

The `wget` command is used to download files from the internet using various protocols such as HTTP, HTTPS, FTP, and more.

It is a versatile tool for downloading files and automating file retrieval tasks from the command line.

`-O discord.deb` option specifies the output filename for the downloaded file. In this case, it will save the downloaded file as `discord.deb` on your local machine.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688264318894/008675c6-436f-4adb-b407-dbde7aa3ed3b.png align="center")

---

## Install Discord

Make sure you are in the same directory where you downloaded the "discord.deb" file before running this command.

In the terminal:

```apache
sudo apt install ./discord.deb
```

The `apt` command is a package management tool commonly used in Debian-based Linux distributions, including Deepin OS. It allows you to manage software packages, install, upgrade, and remove them, as well as resolve dependencies.

`./` refers to the current directory, and `discord.deb` specifies the name of the package file you want to install. In this case, it refers to the `discord.deb` file you previously downloaded.

So, when you execute the `sudo apt install ./discord.deb` command, `apt` will attempt to install the Discord package from the "discord.deb" file located in the current directory.

---

## Troubleshooting

### Download is performed unsanboxed

After using the installation command, I ran into the following issue:

```apache
N: Download is performed unsandboxed as root as file '/home/calaca/discord.deb' couldn't be accessed by user '_apt'. - pkgAcquire::Run (13: Permission denied)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688264896750/4ed36ec7-5b4e-4f7a-93df-a9be77019a9f.png align="center")

Instead of copying and pasting, I wrote the same command again, using the `tab` key in order to find the file.

---

### Error: net::ERR\_CONNECTION\_RESET

After re-running the installation command, I ran into the following issue:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688265191946/b9b3b734-0dc9-4e65-af96-fef91e77e020.png align="center")

I just ignored and I moved on.

---

## Double-check installation

You can choose one of the following options.

---

### Which

The "which" command in Linux is used to locate the executable file associated with a given command or program. It helps you determine the path to the binary file that will be executed when you run a particular command.

When you run the "which" command followed by the name of a command, it searches the directories listed in the "PATH" environment variable to find the corresponding executable file.

In the terminal

```apache
which discord
```

Output

```apache
/usr/bin/discord
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688265346121/cd5159a3-0ed6-4cc7-a667-fdb5f4b9ba29.png align="center")

---

### dpkg

The "dpkg -s" command is useful for checking the status of a specific package, verifying its installation, and retrieving detailed information about it, including its version and description.

```apache
dpkg -s discord
```

Output

```apache
Package: discord
Status: install ok installed
Priority: optional
Section: net
Installed-Size: 223012
Maintainer: Discord Maintainer Team <native-team@discord.com>
Architecture: amd64
Version: 0.0.27
Depends: libc6, libasound2, libatomic1, libgconf-2-4, libnotify4, libnspr4, libnss3, libstdc++6, libxss1, libxtst6, libc++1
Recommends: libappindicator1 | libayatana-appindicator1
Description: Chat for Communities and Friends
 Discord is the easiest way to communicate over voice, video, and text. Chat,
 hang out, and stay close with your friends and communities.
Homepage: https://discord.com
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688265438381/7dd9f467-08ea-4e24-9a6b-074f242cfaf2.png align="center")

---

## Run

```apache
discord & disown
```

\`discord\` is the command to launch the Discord application.

The "&" symbol at the end of the command tells the shell to run Discord in the background, allowing you to continue using the terminal.

"disown" is used to detach the Discord process from the terminal session. This prevents the process from being terminated when you close the terminal.

After running this command, Discord should launch in the background, and you can continue using the terminal for other commands without Discord's output or messages interfering.

---

## **Be happy**

You got here. Way to go!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become business friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome. By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---