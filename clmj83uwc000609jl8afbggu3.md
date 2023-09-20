---
title: "How to generate a SSH key on Linux Mint 21 vanessa or any other Ubuntu-based Linux distribution via the terminal emulator?"
datePublished: Thu Sep 14 2023 13:45:31 GMT+0000 (Coordinated Universal Time)
cuid: clmj83uwc000609jl8afbggu3
slug: how-to-generate-a-ssh-key-on-linux-mint-21-vanessa-or-any-other-ubuntu-based-linux-distribution-via-the-terminal-emulator
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

The `ssh-keygen` is a command-line utility that is used to generate an SSH key pair using the Ed25519 algorithm.

The `-t` flag specifies the type of key to create, key algorithm to use, and in this case, `ed25519` indicates the Ed25519 algorithm.

The `-C` parameter provides a comment (usually your email address) to help you identify the key later.

---

### Enter file

You can choose the path and filename.

If you just want to use the default name, press `Enter`, otherwise, provide the name/path of the file.

```plaintext
Enter file in which to save the key (/home/elitebughunter/.ssh/id_ed25519): /home/elitebughunter/.ssh/ssh_key_mdt
```

Output

```plaintext
elitebughunter@elitebughunter-linux-mint:~$ ssh-keygen -t ed25519 -C "Linux Mint"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/elitebughunter/.ssh/id_ed25519): /home/elitebughunter/.ssh/ssh_key_mdt
Created directory '/home/elitebughunter/.ssh'.
```

---

## Enter passphrase

If you don't want to provide a password, just press `Enter`

```ruby
Created directory '/home/elitebughunter/.ssh'.
Enter passphrase (empty for no passphrase):
```

Output

```ruby
elitebughunter@elitebughunter-linux-mint:~$ ssh-keygen -t ed25519 -C "Linux Mint"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/elitebughunter/.ssh/id_ed25519): /home/elitebughunter/.ssh/ssh_key_mdt
Created directory '/home/elitebughunter/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/elitebughunter/.ssh/ssh_key_mdt
Your public key has been saved in /home/elitebughunter/.ssh/ssh_key_mdt.pub
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

## Check your recently created keys

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