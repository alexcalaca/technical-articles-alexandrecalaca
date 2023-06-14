---
title: "Deepin OS:  How to install Anki on Deepin OS 20.7"
datePublished: Sun Dec 04 2022 14:56:52 GMT+0000 (Coordinated Universal Time)
cuid: clb9hlodh000908mudayoc4rb
slug: deepin-os-how-to-install-anki-on-deepin-os-207
tags: linux, debian, installation, deepin, deepinos

---

`Revisited on June 14th, 2023`

---

Hey guys, how have you been?

Today, we are going to learn how to install `Anki` on Deepin OS 20.7, a Debian based distro.

#### Introduction

`Anki` is a program which makes remembering things easy. Because it's a lot more efficient than traditional study methods, you can either greatly decrease your time spent studying, or greatly increase the amount you learn.

Anki uses the `spaced repetition` concept, which is an evidence-based learning technique that is usually performed with flashcards.

---

#### 0-Run requirements

```apache
sudo apt install libxcb-xinerama0 libxcb-cursor0
```

---

#### 1 - Update your system

Open the terminal and run the following command:

```apache
sudo apt update
```

#### 2 - Download the installer

The official installer can be found [here.](https://apps.ankiweb.net/)

#### 3 - Install zstd

Zstandard, often abbreviated as zstd, is a free, open-source, real-time compression algorithm. It is a fast lossless compression algorithm, targeting real-time compression scenarios at zlib-level and better compression ratios.

```apache
sudo apt install zstd
```

#### 4 - Extract files from the downloaded installer

```apache
tar xaf Downloads/anki-2.1.54-linux-qt6.tar.zst
```

#### 5 - Execute the installer

```apache
cd anki-2.1.XX-linux-qt6
sudo ./install.sh
```

`cd` goes to a new directory.

#### 7 - Open Anki

On terminal, run the following the command:

```apache
anki
```

#### 7 - Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

#### Conclusion

That\`s all for today. I hope this article helped you. Let me know if you have any questions.