---
title: "How to change the port that Vite uses for the local development server"
datePublished: Mon Jan 01 2024 05:35:16 GMT+0000 (Coordinated Universal Time)
cuid: clquhl8xx000408l8a99eeetw
slug: how-to-change-the-port-that-vite-uses-for-the-local-development-server
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704087283874/1d4c7121-6f46-4d25-a5d3-08b72f38e236.webp
tags: javascript, vuejs, reactjs, javascript-framework, vite, alexandrecalaca

---

---

## **Vite**

Vite is a build tool for modern web development that aims to provide a faster and more efficient development experience. It's specifically designed for building web applications using modern JavaScript frameworks such as React, Vue, and others. The name "Vite" is derived from the French word for "fast."

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701960709361/81a5f20c-2703-45ff-83d3-440318836a26.png?auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

---

## Change the flag

```plaintext
npm run dev -- --port 4000
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704086956029/e38e478c-a70d-475d-984c-2af1abd153ab.png align="center")

---

## Change the scripts file

The file is in the root of the application, it's called `package.json`.

Add the following to the `dev`section:

```plaintext
vite --port 3002
```

Result

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704087151687/164d7678-ec76-4ac5-8756-c5f5aa78d190.png align="center")

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704087110432/6f1cce5f-bca3-4602-8192-8aedbde8cfc2.png align="center")

Now, when you run npm run dev, Vite will use port 3002 for the local development server.

---

## **Done**

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

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