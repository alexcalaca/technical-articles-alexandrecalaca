---
title: "How to install Anki on Linux Mint 21 vanessa"
datePublished: Tue Oct 10 2023 11:53:25 GMT+0000 (Coordinated Universal Time)
cuid: clnk9jtyk000009jr5u149cgu
slug: how-to-install-anki-on-linux-mint-21-vanessa
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696935182590/706a9b94-1280-439f-8336-ccf3814fafde.jpeg
tags: ubuntu, linux, learning, anki

---

---

## Anki

`Anki` is a program that makes remembering things easy. Because it's a lot more efficient than traditional study methods, you can either greatly decrease your time spent studying, or greatly increase the amount you learn.

Anki uses the `spaced repetition` concept, which is an evidence-based learning technique that is usually performed with flashcards.

---

## Check your OS

This step is just to make sure you have `Linux Mint` or a \*\*Ubuntu-\*\*based Linux distribution.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
```

---

## **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

---

## Open a Terminal

Open a terminal window on your Linux Mint 21 system. You can typically do this by pressing `Ctrl + Alt + T` or search for "Terminal" in the application launcher.

```apache
Ctrl + Alt + T
```

---

## Run requirements

```apache
sudo apt install libxcb-xinerama0 libxcb-cursor0
```

---

## Update your system

Open the terminal and run the following command:

```apache
sudo apt update
```

The output will look something like the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696623009856/911d4cf8-2288-4b3e-937e-84b0e8281ef1.png align="center")

---

## Download the installer

The official installer can be found directly [here](https://github.com/ankitects/anki/releases/download/2.1.66/anki-2.1.66-linux-qt6.tar.zst) or you can check other alternate versions [in this page.](https://apps.ankiweb.net/)

---

## Install zstd

Zstandard, often abbreviated as zstd, is a free, open-source, real-time compression algorithm. It is a fast lossless compression algorithm, targeting real-time compression scenarios at zlib-level and better compression ratios.

```apache
sudo apt install zstd
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696623191773/4ead9a89-48a2-465a-92f3-c571d004d3eb.png align="center")

---

## Extract files from the downloaded installer

```apache
tar xaf Downloads/anki-2.1.66-linux-qt6.tar.zst -C Downloads/
```

Output

The `tar` command is used for handling archives.

The `x` flag extracts files from an archive.

The `a` flag automatically determine the archive format based on the file extension.

The `f` specifies the archive file to work with. You should follow this option with the name of the archive file.

---

## Execute the installer

```apache
cd Downloads/anki-2.1.66-linux-qt6/
sudo ./install.sh
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696623575229/d90e8d71-8bc4-47f4-bf7f-8e4883a5798e.png align="center")

`cd` goes to a new directory.

---

## Check installation

### Version

```apache
anki --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696934964339/5eb44b1b-2e4e-45df-aa00-ef094716655a.png align="center")

---

### Executable file's path

```apache
which anki
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696934974325/99cfe29f-2e8d-478f-9c20-124e8faee037.png align="center")

---

### Run after installation

```apache
anki
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696935020431/24b7d63b-b0aa-4ad1-88ec-3e863514ee94.png align="center")

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