---
title: "How to create a SSH key on Elementary OS 6.1 or any other Ubuntu-based Linux distribution via the terminal emulator?"
datePublished: Fri Sep 15 2023 04:29:29 GMT+0000 (Coordinated Universal Time)
cuid: clmk3onfy00080aju374lex9r
slug: how-to-create-a-ssh-key-on-elementary-os-61-or-any-other-ubuntu-based-linux-distribution-via-the-terminal-emulator
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694752099781/4029029d-d90b-41f0-8be3-05231ac60cde.png
tags: tutorial, ubuntu, programming-blogs, linux, elementary-os

---

---

## Check your operating system info

### LSB release tool

```plaintext
lsb_release -a
```

The `lsb_release -a` command is used to display detailed information about the Linux distribution on your system.

It stands for "Linux Standard Base release" and provides information such as the distribution's name, release number, codename, and more.

---

### Linux installed info

```plaintext
cat /etc/os-release
```

Running the `cat /etc/os-release` command in the terminal will display the contents of the `/etc/os-release` file, which contains information about the Linux distribution installed on your system.

---

## Generate SSH-key

```plaintext
ssh-keygen -t rsa -b 2048 -C "your email"
```

Replace "your email" with your actual email address.

The `-t` parameter specifies the type of key to create (in this case, RSA).

The `-b` parameter specifies the key length.

The `-C` parameter provides a comment (usually your email address) to help you identify the key later.

---

### Enter file

You can choose the path and filename.

If you just want to use the default name, press `Enter`, otherwise, provide the name/path of the file.

```plaintext
Enter file in which to save the key (/home/elitebughunter/.ssh/id_ed25519):
```

Output

I chose the following as the file name and location:

```plaintext
/home/elitebughunter/.ssh/ssh_key_mnt_elementary
```

---

## Enter passphrase

If you don't want to provide a password, just press `Enter`

```plaintext
Created directory '/home/elitebughunter/.ssh'.
Enter passphrase (empty for no passphrase):
```

---

## Result

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694698076205/7a5a24d2-f59c-4587-afbe-3c9bc82c460f.png align="center")

---

## List all your ssh keys

```plaintext
ls ~/.ssh/
```

---

## Verify the key

```plaintext
cat ~/.ssh/ssh_key_mdt.pub
```

Output

```plaintext
ssh-ed25519 AAZACZNzaZ2lZZI1NZE5ZAAAIOj3BR10R5aZetC7+EY4OIOZuwunQaZww9kxZWdwaZZZ youremail@outlook.com.br
```

---

## Done

---

## **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

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