---
title: "How to hide or show the clock from the system panel in Deepin OS 20.9?"
datePublished: Fri Aug 25 2023 03:41:56 GMT+0000 (Coordinated Universal Time)
cuid: cllq1qlsn000409lb37r19gus
slug: how-to-hide-or-show-the-clock-from-the-system-panel-in-deepin-os-209
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692934770470/98ebacae-8cb9-4117-a58a-eb5f61dd5170.jpeg
tags: linux, deepin, deepinos

---

---

## **Check your OS**

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692754755695/3b882467-a55b-4117-a815-fb6c28c57d21.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692754933720/3c7728bc-29d1-466f-985c-5509f9543035.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

### Current situation

As you can see, my clock is visible.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934217673/72c6a409-04b4-4f85-913e-27f6e560ccba.png align="center")

---

### Open Control Center

`Control Center` is a central hub for configuring various system settings and preferences. It's essentially the control panel or settings app for the Deepin desktop environment. You can access it to customize a wide range of options related to your system.

Two possible ways to access it: dock bar or menu.

---

#### dock

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934396203/6bffe248-41eb-499e-a9c3-8b53da414aed.png align="center")

---

#### menu

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934448418/a4fc7a68-fae2-4647-8644-8a4238172e99.png align="center")

---

### Personalization

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934480469/3c04f5b4-dd72-42c5-8174-2c70e9888daa.png align="center")

---

### Dock

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934532136/3e67fee8-c24b-4f65-b3b3-4dd6a659f7fb.png align="center")

---

### Plugin Area section

Notice the `Datetime` option is set to "checked".

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934593527/73483b10-fc80-4988-95d1-e56392be81ab.png align="center")

---

### Uncheck Datetime option

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934631691/0cf6b8b6-92ee-4755-bccd-9cf1088f9145.png align="center")

---

### Close the window

---

### Check

As you can see, your clock is not available in the Plugin Area anymore.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692934702391/1cb4cd3c-136a-4aab-a059-a15067a11c43.png align="center")

---

### **Done**

---

### **Celebrate**

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

### **Let's connect**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article has helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles. Hope to see you next time.

---