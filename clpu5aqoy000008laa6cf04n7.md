---
title: "Creating a customized SSH key on Pop!_OS 22.04: step-by-step with screenshots"
datePublished: Wed Dec 06 2023 19:11:28 GMT+0000 (Coordinated Universal Time)
cuid: clpu5aqoy000008laa6cf04n7
slug: creating-a-customized-ssh-key-on-popos-2204-step-by-step-with-screenshots
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/C1P4wHhQbjM/upload/e403f734d2cc7c2bd2b932e2226db8e5.jpeg
tags: ubuntu, linux, popos, alexandrecalaca

---

---

## **SSH**

SSH, which stands for Secure Shell, is a cryptographic network protocol used for secure communication over an unsecured network. It is commonly used to access and manage remote systems securely.

SSH provides a secure channel over an insecure network by using strong encryption to protect the communication between a client and a server, preventing eavesdropping, connection hijacking, and other attacks.

---

## SSH key

An SSH key is a pair of cryptographic keys used for secure communication between a client and a server using the SSH (Secure Shell) protocol. The two components of an SSH key pair are the private key and the public key.

Using SSH keys for authentication is considered more secure than traditional password-based authentication. The private key acts as a form of digital signature, and even if someone gains access to the public key, they cannot easily derive the corresponding private key.

---

### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

### **List all SSH keys**

```plaintext
ls ~/.ssh/
```

---

### **Generate the SSH key**

```plaintext
ssh-keygen -t ed25519 -C "Alexandre Calaca EBH Pop!_OS SSH Key" -f ~/.ssh/ebh_pop-os_ssh_key
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701889232194/b9392b7c-4b2a-44dd-8c4d-6584f99cc374.png align="center")

---

## **Enter your passphrase**

Leave it empty if you prefer.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701889597691/4904245f-9696-4059-9a88-6fad0296c51f.png align="center")

---

## Visualize your SSH key

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701889663047/7585d800-011d-4b5d-9a9d-468def48c926.png align="center")

---

## List your keys

```plaintext
ls ~/.ssh/
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701889753840/cf68038a-3948-4e60-87ab-d6a43d3988c4.png align="center")

---

## Done

---

## Celebrate

Well-done. You did a great job!

![Casts Of The Office Celebration Dance GIF | GIFDB.com](https://gifdb.com/images/high/casts-of-the-office-celebration-dance-p9rrkj7pyawhjo54.gif align="left")

---

## **Let's network**

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