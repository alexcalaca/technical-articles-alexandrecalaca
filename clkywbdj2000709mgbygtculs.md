---
title: "How to remove the Transparency window effect on Deepin OS 20.7?"
datePublished: Sun Aug 06 2023 03:40:21 GMT+0000 (Coordinated Universal Time)
cuid: clkywbdj2000709mgbygtculs
slug: how-to-remove-the-transparency-window-effect-on-deepin-os-207
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/eUrRZKFds9k/upload/d1182d834accb72055bf991acbf8f8d4.jpeg
tags: ubuntu, debian, deepin

---

---

## Introduction

Deepin OS uses its own desktop environment called DDE, which is designed to be visually appealing, smooth, and intuitive. It offers a macOS-like experience with a dock, launcher, and a system tray.

---

## Solution

Let's go over the solution.

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

## Desktop Settings

Right click on desktop and choose `Desktop Settings`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691292445587/468a109f-932f-496b-8262-69ee100fdfc2.png align="center")

---

## Personalization

Click on `Personolization`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691292492551/1a5e49b4-182d-4f90-9296-f20779790d4a.png align="center")

---

## Window Effect

Look for `Window Effect` option.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691292601587/c36c8456-fd90-45ba-ae48-8c6d1c4df43b.png align="center")

As you can see, your `Window Effect` is set to true.

---

## Uncheck Window Effect

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691292666167/0f40baaf-956d-4341-91f1-c9c8ae9ce580.png align="center")

---

## Save changes

Just click on the `close` button.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691292743605/116f8135-70cc-4a34-84ca-3b2900793f4b.png align="center")

---

## **Done**

You've made it!

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

## **Let's connect**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---