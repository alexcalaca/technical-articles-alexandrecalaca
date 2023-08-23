---
title: "How to change the default Terminal emulator  in Deepin OS 20.9?"
datePublished: Wed Aug 23 2023 12:10:06 GMT+0000 (Coordinated Universal Time)
cuid: cllnp0f09000e09joghxo5p92
slug: how-to-change-the-default-terminal-emulator-in-deepin-os-209
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692792573263/1e03efc2-dde6-4c91-936d-fc4f15c79e9f.jpeg
tags: linux, terminal, deepin, deepinos

---

---

## Check your OS

Just in case you're not sure if you have the operating system Deepin OS installed. Let's take how a look how you can find out.

---

### Linux Standard Base approach

The command `lsb_release -a` is used to display information about the Linux Standard Base (LSB) and distribution-specific information of your Linux system.

The `lsb_release` command is useful for identifying the distribution and its version in a standardized manner, particularly if you are writing scripts or need to retrieve distribution information programmatically.

In your terminal:

```apache
lsb_release -a
```

Your output might look like the following:

```apache
No LSB modules are available.
Distributor ID: Deepin
Description:    Deepin 20.9
Release:        20.9
Codename:       apricot
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692754755695/3b882467-a55b-4117-a815-fb6c28c57d21.png?auto=compress,format&format=webp align="left")

---

### Operating System release

The `cat /etc/os-release` command is used to display information about the operating system (OS) release in a Linux-based system.

This information can be particularly useful for scripting and automation tasks when you need to determine the distribution and version of the Linux system you are working with. It provides a standardized way to access this information across different Linux distributions.

In your terminal:

```apache
cat /etc/os-release
```

Your output might look like the following:

```apache
calaca@calaca-PC ~ $ cat /etc/os-release
PRETTY_NAME="Deepin 20.9"
NAME="Deepin"
VERSION_ID="20.9"
VERSION="20.9"
VERSION_CODENAME="apricot"
ID=Deepin
HOME_URL="https://www.deepin.org/"
BUG_REPORT_URL="https://bbs.deepin.org/"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692754933720/3c7728bc-29d1-466f-985c-5509f9543035.png?auto=compress,format&format=webp align="left")

---

## Open Control Center

The Control Center in Deepin OS serves as a centralized hub for configuring various system settings and managing your desktop environment. It provides a user-friendly and intuitive way to customize your system preferences.

Let me show you two ways.

---

### In your dock menu bar

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692791774760/8404ab0b-4fe8-4cc3-8c05-dd766a103e0c.png align="center")

---

### Main menu

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692791851181/cd3e17ae-bb2b-4274-a895-7b4f0b81a0f5.png align="center")

---

### Default Applications

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692791884668/0f646567-1393-452f-9805-9f42f85d597f.png align="center")

---

### Terminal

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692791906863/f0944b11-059c-4158-b7b2-fd78f7857e77.png align="center")

---

### Check your current terminal

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692791939796/5abfe3c4-bf4d-45ce-bede-024dd912b919.png align="center")

---

### Change default terminal

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692792001835/b7af2d3a-4f94-4fb9-96c5-3f02364eda1f.png align="center")

It's not necessary to click on Ok. Just choose it and close the window.

---

### Open default terminal

Press the shortcut `CTRL + ALT + T`. In case it does not work, you'll have to configure this shortcut to open the default terminal.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692792478492/51ec3358-03f7-4ade-95ea-9c1812af0d61.png align="center")

---

### Done

---

### **Done**

Restart your server

---

## **Celebrate**

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