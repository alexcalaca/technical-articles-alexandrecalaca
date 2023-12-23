---
title: "Deepin OS:  How to install Anki on Deepin OS 20.7"
datePublished: Sun Dec 04 2022 14:56:52 GMT+0000 (Coordinated Universal Time)
cuid: clb9hlodh000908mudayoc4rb
slug: deepin-os-how-to-install-anki-on-deepin-os-207
tags: tutorial, ubuntu, linux, debian, installation, deepin, deepinos, alexandrecalaca

---

`Revisited on December 23rd, 2023`

---

Hey guys, how have you been?

Today, we are going to learn how to install `Anki` on Deepin OS 20.7, a Debian based distro.

---

### Introduction

`Anki` is a program which makes remembering things easy. Because it's a lot more efficient than traditional study methods, you can either greatly decrease your time spent studying, or greatly increase the amount you learn.

Anki uses the `spaced repetition` concept, which is an evidence-based learning technique that is usually performed with flashcards.

---

### Run requirements

```apache
sudo apt install libxcb-xinerama0 libxcb-cursor0
```

---

### **Update packages info**

```
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.Open the terminal and run the following command:

---

### Download the installer

The official installer can be found directly [**here**](https://github.com/ankitects/anki/releases/download/2.1.66/anki-2.1.66-linux-qt6.tar.zst) or you can check other alternate versions [**in this page.**](https://apps.ankiweb.net/)

---

### Install zstd

Zstandard, often abbreviated as zstd, is a free, open-source, real-time compression algorithm. It is a fast lossless compression algorithm, targeting real-time compression scenarios at zlib-level and better compression ratios.

```apache
sudo apt install zstd
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703298876382/c364845f-0534-4bef-a6fe-eecf4c9b4458.png?auto=compress,format&format=webp align="left")

---

### Extract files from the downloaded installer

```apache
tar xaf Downloads/anki-2.1.54-linux-qt6.tar.zst
```

**Output**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299088739/e9f14475-3a7e-482d-8134-801cf1e9e85c.png?auto=compress,format&format=webp align="left")

Output

The `tar` command is used for handling archives.

The `x` flag extracts files from an archive.

The `a` flag automatically determine the archive format based on the file extension.

The `f` specifies the archive file to work with. You should follow this option with the name of the archive file.

---

### Execute the installer

```apache
cd anki-2.1.XX-linux-qt6
sudo ./install.sh
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299252891/e6a40ab0-5758-47ff-be59-0b554cc9fb10.png?auto=compress,format&format=webp align="left")

`cd` goes to a new directory.

---

## **Check installation**

### Version

```plaintext
anki --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299326706/a54a5d19-a846-4ef2-a46c-5b67dda0b738.png?auto=compress,format&format=webp align="left")

---

### Executable file's path

```plaintext
which anki
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299404919/4f098879-985e-4229-bcb7-5d87cc932c1b.png?auto=compress,format&format=webp align="left")

---

### Open Anki

On terminal, run the following the command:

```apache
anki
```

---

### Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

---

### **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---