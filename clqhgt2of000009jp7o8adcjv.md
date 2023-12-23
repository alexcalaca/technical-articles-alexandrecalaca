---
title: "Setting up Anki on Pop!_OS 22.04: A step by step guide"
datePublished: Sat Dec 23 2023 02:52:22 GMT+0000 (Coordinated Universal Time)
cuid: clqhgt2of000009jp7o8adcjv
slug: setting-up-anki-on-popos-2204-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703299861108/3c993aea-f4f8-4601-902c-4ec05ac6bab4.png
tags: tutorial, ubuntu, linux, popos, alexandrecalaca

---

## **Anki**

`Anki` is a program which makes remembering things easy. Because it's a lot more efficient than traditional study methods, you can either greatly decrease your time spent studying, or greatly increase the amount you learn.

Anki uses the `spaced repetition` concept, which is an evidence-based learning technique that is usually performed with flashcards.

---

## **Let's get down to business**

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="left")

---

### **Check your OS (optional)**

This step is just to make sure you have `Pop!_OS` installed.

```plaintext
uname -a
hostnamectl
lsb_release -a
cat /etc/os-release
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## **Update packages info**

```plaintext
sudo apt-get update
```

Running `sudo apt-get update` is an important step before installing or upgrading packages on your system because it ensures that you have the most up-to-date information about available packages.

Without updating the package index, you might not see the latest versions of software or be able to install new packages that have been added to the repositories since the last update.

---

## Install requirements

```plaintext
sudo apt install libxcb-xinerama0 libxcb-cursor0
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703298739936/c6f77f6b-4784-45db-be01-c00a81ba01be.png align="center")

---

## **Download the installer**

The official installer can be found directly [**here**](https://github.com/ankitects/anki/releases/download/2.1.66/anki-2.1.66-linux-qt6.tar.zst) or you can check other alternate versions [**in this page.**](https://apps.ankiweb.net/)

---

## **Install zstd**

Zstandard, often abbreviated as zstd, is a free, open-source, real-time compression algorithm. It is a fast lossless compression algorithm, targeting real-time compression scenarios at zlib-level and better compression ratios.

```plaintext
sudo apt install zstd
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703298876382/c364845f-0534-4bef-a6fe-eecf4c9b4458.png align="center")

---

## **Extract files from the downloaded installer**

```plaintext
tar xaf ~/Downloads/anki-2.1.66-linux-qt6.tar.zst -C ~/Downloads/
```

**Output**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299088739/e9f14475-3a7e-482d-8134-801cf1e9e85c.png align="center")

Output

The `tar` command is used for handling archives.

The `x` flag extracts files from an archive.

The `a` flag automatically determine the archive format based on the file extension.

The `f` specifies the archive file to work with. You should follow this option with the name of the archive file.

---

## Execute the installer

```plaintext
cd ~/Downloads/anki-2.1.66-linux-qt6/
sudo ./install.sh 
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299252891/e6a40ab0-5758-47ff-be59-0b554cc9fb10.png align="center")

---

## **Check installation**

### Version

```plaintext
anki --version
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299326706/a54a5d19-a846-4ef2-a46c-5b67dda0b738.png align="center")

---

### Executable file's path

```plaintext
which anki
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299404919/4f098879-985e-4229-bcb7-5d87cc932c1b.png align="center")

---

### Run after installation

```plaintext
anki
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299471732/5be158df-5396-4b51-8dba-8d6cd9548547.png align="center")

---

## Configure Anki

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299497902/05e18788-9e19-47f5-8c68-8341beb98302.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299520413/9f3ca618-42a7-4189-9923-31b872de78c2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299535300/6624a118-3cf2-409d-a6c5-b2fa5c750883.png align="center")

---

## Sync with your web account

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299627260/117d685f-95d3-4ad8-8619-f27c727d33a3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299673197/83b7356a-a9f2-43a4-b2a0-a1d57520e4b1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703299700012/8fce8b80-6f34-420e-9522-4ce8e8ca08bd.png align="center")

---

## **Done**

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="center")

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

---