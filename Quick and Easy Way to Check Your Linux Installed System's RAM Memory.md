---
title: "Quick and Easy Way to Check Your Linux Installed System's RAM Memory"
datePublished: Thu May 04 2023 11:12:35 GMT+0000 (Coordinated Universal Time)
cuid: clh912w4n000209ju87vicfjm
slug: quick-and-easy-way-to-check-your-linux-installed-systems-ram-memory
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/s71GAZsTs-g/upload/36ead631a1bff2b62ea4b6ebdc67c6fd.jpeg
tags: ubuntu, programming-blogs, linux, hashnode, 2articles1week

---

---

### Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. I'm so excited that you landed here. Hope you enjoy this new article.

By the way, I would be glad to receive your feedback about this one and other articles.

---

### Introduction

This article `Quick and Easy Way to Check Your Linux Installed System's RAM Memory` is going to show how

---

### Check your OS

```apache
lsb_release -a
```

If you have Ubuntu, you'll end up with something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683148216396/22623636-279f-498e-8c66-43e2919b06ba.png align="center")

If you have another distribution, such as `Deepin Os`. You'll see something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683148270565/f7085010-030c-4763-a3c2-b2b2a6c2e8cb.png align="center")

---

#### The LSB command

The `lsb_release -a` command is used to display certain LSB (Linux Standard Base) and distribution-specific information about the Linux distribution you are running.

It prints the following information:

* Distributor ID
    
* Description
    
* Release
    
* Codename
    
    This command is available on most modern Linux distributions that use the LSB. However, some smaller or less mainstream distributions may not have the command installed by default. In that case, you may need to install the lsb-release package to get access to the lsb\_release command.In programming, a collection refers to a data structure that stores a group of related elements. Collections are used to organize and manage data in a way that makes it easy to access and manipulate.
    

---

### Verify your installed RAM

Open the terminal and run the following command:

```apache
sudo dmidecode --type 17
```

On Ubuntu, you'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683197150096/ddbfdf1d-4794-40d9-8491-62db077460af.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683197161154/dfda6d71-ae38-45c6-9423-e7b496442211.png align="center")

On Deepin Os, you'll see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683198687856/9430ed5a-f2ee-4d5b-aedb-896df2ea44d3.png align="center")

---

### dmidecode command

The `sudo dmidecode --type 17` command is a Linux command used to display information about memory devices installed on a computer system.

Specifically, it uses the `dmidecode` tool to retrieve the System Memory Array information, which includes details about the maximum capacity, type, and number of memory slots available on the system.

The `dmidecode` tool reads the system's DMI, which stands for Desktop Management Interface data, which is a standardized way to describe a computer's hardware components, such as the motherboard, BIOS, and peripherals.

By specifying `--type 17`, the command filters the output to only show information about the memory devices. The output includes details such as the manufacturer, part number, serial number, size, speed, and type of memory modules installed on the system.

---

### Summary

In this article, we learned how to use the `dmidecode` command. dmi stands for Desktop Management Interface data.

We used the `--type 17` argument, by using it, it output only information about the memory devices.

---

### Celebrate

If you read the article, kudos! you did a great job. You can celebrate for sure!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

### Conclusion

That's all for today. Thanks for reading the article `Quick and Easy Way to Check Your Linux Installed System's RAM Memory.`

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.
