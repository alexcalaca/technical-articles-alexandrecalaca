---
title: "How to create a SSH key in Deepin OS 20.7 via the terminal emulator?"
datePublished: Thu Sep 14 2023 13:45:31 GMT+0000 (Coordinated Universal Time)
cuid: clmj83uwc000609jl8afbggu3
slug: how-to-create-a-ssh-key-in-deepin-os-207-via-the-terminal-emulator
tags: tutorial, ubuntu, linux, debian, deepin

---

---

## Generate SSH-key

```plaintext
ssh-keygen -t ed25519 -C "your email"
```

Replace "your email" with your actual email address.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694697853385/2db823b4-246d-4968-8024-88e26a96698e.png align="center")

The command is used to generate an SSH key pair using the Ed25519 algorithm. The `-t` flag specifies the type of key algorithm to use, and in this case, `ed25519` indicates the Ed25519 algorithm.

Here's a breakdown of the command and its components:

1. `ssh-keygen`: This is the command-line utility for generating SSH keys.
    
2. `-t ed25519`: The `-t` flag specifies the key type to be generated, and `ed25519` indicates the Ed25519 algorithm. Ed25519 is a modern elliptic curve cryptographic algorithm known for its strong security and performance.
    

---

### Enter file

You can choose the path and filename.

If you just want to use the default name, press `Enter`, otherwise, provide the name/path of the file.

```plaintext
Enter file in which to save the key (/home/elitebughunter/.ssh/id_ed25519):
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694697980076/1be780b3-5604-42ab-ac41-2f458d547253.png align="center")

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

## Check your recent created keys

```plaintext
cat ~/.ssh/ssh_key_mdt.pub
```

Output

```plaintext
ssh-ed25519 AAZACZNzaZ1lZZI1NZE5ZAAAIOj3BR10R5aZetC7+EY4OIOZuwunQaZww9kxZWdwaZZZ youremail@outlook.com.br
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