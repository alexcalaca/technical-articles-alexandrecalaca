---
title: "How to generate an SSH key on Fedora 38"
datePublished: Fri Nov 10 2023 02:48:59 GMT+0000 (Coordinated Universal Time)
cuid: clos0r40q00030al89f27bxzn
slug: how-to-generate-an-ssh-key-on-fedora-38
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jJnZg7vBfMs/upload/f9f5eb62f0916f8ade559b6a4cbac418.jpeg
tags: fedora, linux-for-beginners, linux-basics, alexandrecalaca

---

---

## SSH

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

## **Check your OS (optional)**

This step is just to ensure you have **Fedora 38 Linux installed. You can pick up one command or you can use them all.**

### /etc/os-release

```ruby
cat /etc/os-release
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910445814/c08acc61-4276-4d0c-885a-27e3c1a07536.png?auto=compress,format&format=webp align="left")

---

### hostnamectl

```ruby
hostnamectl
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910683442/f37384f0-4274-498a-8130-82c4d90d01aa.png?auto=compress,format&format=webp align="left")

When you run `hostnamectl` without any options, it provides detailed information about the system's hostname, operating system, kernel, and other system-related settings.

---

## lsb\_release

```ruby
lsb_release -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910719446/6460fa24-aa93-4c5c-9101-d45a5b382fe8.png?auto=compress,format&format=webp align="left")

`lsb_release` is a command-line utility commonly found in Linux distributions that adhere to the Linux Standard Base (LSB). The LSB is a standardization initiative that aims to increase compatibility between different Linux distributions by defining a common set of libraries and conventions.

---

### uname

```ruby
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910869580/e24b0907-cf0f-4a3f-924e-021fb67670a4.png?auto=compress,format&format=webp align="left")

The `uname -a` command is used to display detailed system information about the Linux operating system. It provides information about the system's kernel and other system-related details.

---

## **Generate the SSH key**

```ruby
ssh-keygen -t ed25519 -C "Elite Bug Hunter Fedora SSH Key" -f ~/.ssh/ebh_fedora_ssh_key
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699582989625/719f040b-4582-476c-a700-f9e43b7d9364.png align="center")

---

### Brief explanation

* `-t ed25519`: Specifies the type of key to create, in this case, Ed25519.
    
* `-C "Elite Bug Hunter Fedora SSH Key"`: Adds a comment to the key. Make sure to include the comment in double quotes.
    
* `-f ~/.ssh/ebh_fedora_ssh_key`: Specifies the filename of the key.
    

---

## Enter your password

You will be prompted to enter a passphrase. You can either enter a passphrase or press Enter to create the key without a passphrase.

If you want to keep it empty, just press `Enter` twice.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699583129153/3a78a63c-de6a-4266-9533-24d908c79f53.png align="center")

---

## Visualize your key

```ruby
elitebughunter@fedora ~ $ ssh-keygen -t ed25519 -C "Elite Bug Hunter Fedora SSH Key" -f ~/.ssh/ebh_fedora_ssh_key
Generating public/private ed25519 key pair.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/elitebughunter/.ssh/ebh_fedora_ssh_key
Your public key has been saved in /home/elitebughunter/.ssh/ebh_fedora_ssh_key.pub
The key fingerprint is:
SHA256:4/W4zCVzSmzpObHyoejgJgDtthyNKjOAUkTGEudfbqE Elite Bug Hunter Fedora SSH Key
The key's randomart image is:
+--[ED25519 256]--+
|o.+ . F          |
|oO * o     .     |
|Y.X.Y     +      |
|o%o@ +   o .  o   |
|..= = . S o + .  |
|       + - * o   |
|      o . 2 o    |
|       . . 1     |
|          o      |
+----[SHA256]-----+
elitebughunter@fedora ~ $
```

After completing these steps, your new SSH key pair will be generated. The private key will be saved to `~/.ssh/ebh_fedora_ssh_key` and the public key will be saved to `~/.ssh/ebh_fedora_ssh_key.pub`.

---

## Check the keys

```ruby
ls ~/.ssh/
ls ~/.ssh/ | grep ebh
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699583438242/deee037b-9f53-4ec3-9cf7-5aadba4c611b.png align="center")

---

## Done

---

## Celebrate

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/elitebughunter)
    
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