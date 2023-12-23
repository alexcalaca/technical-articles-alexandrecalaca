---
title: "How to install Homebrew on Deepin OS or any other Debian-based linux distribution"
datePublished: Tue Sep 12 2023 10:41:33 GMT+0000 (Coordinated Universal Time)
cuid: clmg6nkem002s09jiah8o8bcy
slug: how-to-install-homebrew-on-deepin-os-or-any-other-debian-based-linux-distribution
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694491818926/ce8b57fa-3bf2-4017-a52d-3724072d44af.png
tags: ubuntu, operating-system, linux, homebrew

---

---

## Install the building blocks

The sudo `apt-get install build-essential` command is used to install a set of essential development tools and packages on a Debian-based Linux system.

These tools and packages are commonly needed when you want to compile and build software from source code on your system.

```apache
sudo apt-get install build-essential
```

Output

```apache
calaca@calaca-PC ~ $ sudo apt-get install build-essential
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  deepin-pw-check fonts-lato gstreamer1.0-fluendo-mp3 imageworsener libatkmm-1.6-1v5 libcairomm-1.0-1v5 libdavs2-16 libdeepin-authenticate libdframeworkdbus-dev
  libdumbnet1 libgtkmm-3.0-1v5 libjs-jquery libllvm11 libmaxminddb0 libmspack0 libnppc11 libnppicc11 libnppidei11 libnppig11 libpangomm-1.4-1v5 libqtermwidget5-0
  libsmi2ldbl libwireshark-data libwireshark11 libwiretap8 libwscodecs2 libwsutil9 libxavs2-13 libxmlsec1 libxmlsec1-openssl qtermwidget5-data ruby-did-you-mean
  ruby-minitest ruby-net-telnet ruby-power-assert ruby-test-unit ruby-xmlrpc rubygems-integration x11-apps x11-session-utils xinit
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  build-essential
0 upgraded, 1 newly installed, 0 to remove and 6 not upgraded.
Need to get 7,576 B of archives.
After this operation, 20.5 kB of additional disk space will be used.
Get:1 https://community-packages.deepin.com/deepin apricot/main amd64 build-essential amd64 12.6 [7,576 B]
Fetched 7,576 B in 3s (2,261 B/s)           
Selecting previously unselected package build-essential.
(Reading database ... 280461 files and directories currently installed.)
Preparing to unpack .../build-essential_12.6_amd64.deb ...
Unpacking build-essential (12.6) ...
Setting up build-essential (12.6) ...
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691587013372/d36dc67d-8462-40f0-8659-955d98091506.png align="center")

---

## Git

```apache
git --version
```

Output

```apache
calaca@calaca-PC ~ $ git --version
git version 2.20.1
```

---

## Compiler

In the context of Linux Debian, the `make` command is a build automation tool used to compile and build software from source code. It is a critical component of the software development process on Linux systems.

```apache
which make
```

Output

```apache
calaca@calaca-PC ~ $ which make
/usr/bin/make
```

---

## Download the script

```apache
curl -fsSL -o install.sh https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
```

Output

```apache
calaca@calaca-PC ~ $ curl -fsSL -o install.sh https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
```

---

### Check the script's content

```apache
less install.sh
```

Output

```apache
#!/bin/bash

# We don't need return codes for "$(command)", only stdout is needed.
# Allow `[[ -n "$(command)" ]]`, `func "$(command)"`, pipes, etc.
# shellcheck disable=SC2312

set -u

abort() {
  printf "%s\n" "$@" >&2
  exit 1
}

# Fail fast with a concise message when not using bash
# Single brackets are needed here for POSIX compatibility
# shellcheck disable=SC2292
if [ -z "${BASH_VERSION:-}" ]
then
  abort "Bash is required to interpret this script."
fi

# Check if script is run with force-interactive mode in CI
if [[ -n "${CI-}" && -n "${INTERACTIVE-}" ]]
then
  abort "Cannot run force-interactive mode in CI."
fi

# Check if both `INTERACTIVE` and `NONINTERACTIVE` are set
# Always use single-quoted strings with `exp` expressions
# shellcheck disable=SC2016
if [[ -n "${INTERACTIVE-}" && -n "${NONINTERACTIVE-}" ]]
then
  abort 'Both `$INTERACTIVE` and `$NONINTERACTIVE` are set. Please unset at least one variable and try again.'
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691589755284/2b160c4f-ac1f-4946-838d-021009250264.png align="center")

---

## Install

```apache
/bin/bash install.sh
```

Initial output

```apache
calaca@calaca-PC ~ $ /bin/bash install.sh
==> Checking for `sudo` access (which may request your password)...
[sudo] password for calaca: 
Verification successful
==> This script will install:
/home/linuxbrew/.linuxbrew/bin/brew
/home/linuxbrew/.linuxbrew/share/doc/homebrew
/home/linuxbrew/.linuxbrew/share/man/man1/brew.1
/home/linuxbrew/.linuxbrew/share/zsh/site-functions/_brew
/home/linuxbrew/.linuxbrew/etc/bash_completion.d/brew
/home/linuxbrew/.linuxbrew/Homebrew
==> The following new directories will be created:
/home/linuxbrew/.linuxbrew/bin
/home/linuxbrew/.linuxbrew/etc
/home/linuxbrew/.linuxbrew/include
/home/linuxbrew/.linuxbrew/lib
/home/linuxbrew/.linuxbrew/sbin
/home/linuxbrew/.linuxbrew/share
/home/linuxbrew/.linuxbrew/var
/home/linuxbrew/.linuxbrew/opt
/home/linuxbrew/.linuxbrew/share/zsh
/home/linuxbrew/.linuxbrew/share/zsh/site-functions
/home/linuxbrew/.linuxbrew/var/homebrew
/home/linuxbrew/.linuxbrew/var/homebrew/linked
/home/linuxbrew/.linuxbrew/Cellar
/home/linuxbrew/.linuxbrew/Caskroom
/home/linuxbrew/.linuxbrew/Frameworks
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691590342550/c64f1367-b547-4822-a347-cd2a2af0ffc3.png align="center")

---

## Add homebrew to your path

```apache
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/calaca/.bash_profile
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

Output

```apache
calaca@calaca-PC ~/var/www $ (echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/calaca/.bash_profile
calaca@calaca-PC ~/var/www $  eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

---

## Install homebrew's dependencies

```apache
sudo apt-get install build-essential
```

Output

```apache
calaca@calaca-PC ~/var/www $ sudo apt-get install build-essential
[sudo] password for calaca: 
Verification successful
Reading package lists... Done
Building dependency tree       
Reading state information... Done
build-essential is already the newest version (12.6).
The following packages were automatically installed and are no longer required:
  deepin-pw-check fonts-lato gstreamer1.0-fluendo-mp3 imageworsener libatkmm-1.6-1v5 libcairomm-1.0-1v5 libdavs2-16 libdeepin-authenticate libdframeworkdbus-dev
  libdumbnet1 libgtkmm-3.0-1v5 libjs-jquery libllvm11 libmaxminddb0 libmspack0 libnppc11 libnppicc11 libnppidei11 libnppig11 libpangomm-1.4-1v5 libqtermwidget5-0
  libsmi2ldbl libwireshark-data libwireshark11 libwiretap8 libwscodecs2 libwsutil9 libxavs2-13 libxmlsec1 libxmlsec1-openssl qtermwidget5-data ruby-did-you-mean
  ruby-minitest ruby-net-telnet ruby-power-assert ruby-test-unit ruby-xmlrpc rubygems-integration x11-apps x11-session-utils xinit
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 6 not upgraded.
```

---

## Confirm brew's installation

```apache
which brew
```

Output

```apache
calaca@calaca-PC ~/var/www $ which brew
/home/linuxbrew/.linuxbrew/bin/brew
```

---

## Check's version

```apache
brew -v
```

or

```apache
brew --version
```

Output:

```apache
calaca@calaca-PC ~/var/www $ brew --version
Homebrew 4.1.4
```

---

## Install gcc

```apache
brew install gcc
```

Initial output

```apache
calaca@calaca-PC ~/var/www $ brew install gcc
==> Fetching dependencies for gcc: linux-headers@5.15, glibc, gmp, isl, mpfr, libmpc, lz4, xz, zlib, zstd and binutils
==> Fetching linux-headers@5.15
==> Downloading https://ghcr.io/v2/homebrew/core/linux-headers/5.15/manifests/5.15.125
################################################################################################################################################################### 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/linux-headers/5.15/blobs/sha256:ba7a48a44cfc8eea5b77d0a2408dbaea0c8b69a5823ee0fcb15cf36e8e307a10
################################################################################################################################################################### 100.0%
==> Fetching glibc
==> Downloading https://ghcr.io/v2/homebrew/core/glibc/manifests/2.35_1
################################################################################################################################################################### 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/glibc/blobs/sha256:274dd06ae6ecaee3025d6bf21cf4c7641df9a1cc3973e162911a1f4a76000a24
################################################################################################################################################################### 100.0%
==> Fetching gmp
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/manifests/6.2.1_1
################################################################################################################################################################### 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/blobs/sha256:786ae29f0c0b06ea86e42bd9c6ac2c49bd5757da037dead7053e8bd612c4cf8c
################################################################################################################################################################### 100.0%
==> Fetching isl
==> Downloading https://ghcr.io/v2/homebrew/core/isl/manifests/0.26
################################################################################################################################################################### 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/isl/blobs/sha256:db14ba1e4ea23ab41e06930dcf25ae9023c5e395c88602da2a9b6a98d54c92d3
################################################################################################################################################################### 100.0%
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691591515063/5234f426-9330-41ee-9c05-7e7bce2bb26a.png align="center")

---

## Install tree

```apache
brew install tree
```

Output:

```apache
calaca@calaca-PC ~/var/www $ brew install tree

==> Fetching tree
==> Downloading https://ghcr.io/v2/homebrew/core/tree/manifests/2.1.1
################################################################################################################################################################### 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/tree/blobs/sha256:def7fe0895d7e8d0d9c5090effa68e1536a090a613932938ae38fde80e7b2354
################################################################################################################################################################### 100.0%
==> Pouring tree--2.1.1.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/tree/2.1.1: 8 files, 193KB
==> Running `brew cleanup tree`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691592154362/50fdb49c-28d4-4389-bf91-7f754ade9b70.png align="center")

---

## "Run" brew

```apache
brew doctor
```

Output

```apache
calaca@calaca-PC ~/var/www $ brew doctor
Your system is ready to brew.
```

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
