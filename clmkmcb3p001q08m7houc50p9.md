---
title: "how to add nameserver addresses manually  to the DNS configuration on Deepin OS 20.9?"
datePublished: Fri Sep 15 2023 13:11:46 GMT+0000 (Coordinated Universal Time)
cuid: clmkmcb3p001q08m7houc50p9
slug: how-to-add-nameserver-addresses-manually-to-the-dns-configuration-on-deepin-os-209
tags: tutorial, ubuntu, linux, debian, deepin

---

---

## Check DNS configuration

```apache
cat /etc/resolv.conf 
```

---

## Open the file

```apache
sudo code /etc/resolv.conf
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694777723692/423b83c0-6732-424e-9a32-73413ba7aa14.png align="center")

---

## Add the nameserver addresses

Before the changes

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694777723692/423b83c0-6732-424e-9a32-73413ba7aa14.png align="center")

After the changes

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694777802104/d644cdad-07cd-4b56-ae5f-4443085f42e8.png align="center")

---

## Double-check changes

```apache
cat /etc/resolv
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694777911894/d2ca8b7a-08b6-4954-ac1c-5497d4d082df.png align="center")

---

## Apply the changes

> Use it with caution. This will restart your network. While it wasn't necessary for my personal needs, it might be required for yours.

```apache
sudo service NetworkManager restart
```

---

## **Done**

---

## **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's work together**

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