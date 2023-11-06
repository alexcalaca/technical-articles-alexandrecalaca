---
title: "Resolving Docker  Desktop 'Unable to log in' warning on Fedora 38 due to Pass initialization"
datePublished: Mon Nov 06 2023 13:46:22 GMT+0000 (Coordinated Universal Time)
cuid: clomyh350000f08l77js39kjy
slug: resolving-docker-desktop-unable-to-log-in-warning-on-fedora-38-due-to-pass-initialization
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699276848738/b322d391-d187-4b2a-9169-b1493683db1a.png
tags: docker, development, fedora, alexandrecalaca

---

---

# **Unable to log in**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699276830609/889aca28-468c-49b0-88c4-6ddfb0cc094b.png align="left")

Docker Desktop relies on [`pass`](https://www.passwordstore.org/)to store credentials in gpg2-encrypted files.

Before signing in to Docker Hub from the Docker Dashboard or the Docker menu, you must initialize `pass`. Docker Desktop displays a warning if you've not initialized `pass`.

---

### Pass

`Pass` is the standard unix password manager.

With `pass`, each password lives inside of a [`gpg`](http://en.wikipedia.org/wiki/GNU_Privacy_Guard) encrypted file whose filename is the title of the website or resource that requires the password. These encrypted files can be manipulated using standard command line file management utilities.

`pass` makes managing these individual password files extremely easy. All passwords live in `~/.password-store`, and `pass` provides some nice commands for adding, editing, generating, and retrieving passwords.

It is a very short and simple shell script. It's capable of temporarily putting passwords on your clipboard and tracking password changes using [`git`](http://en.wikipedia.org/wiki/Git_(software)).

---

#### **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

## Solution

---

## **Check your OS (optional)**

This step is just to ensure you have **Fedora 38 Linux installed. You can pick up one command or you can use them all.**

### /etc/os-release

**COPY**

**COPY**

```ruby
cat /etc/os-release
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697910445814/c08acc61-4276-4d0c-885a-27e3c1a07536.png?auto=compress,format&format=webp align="left")

---

### hostnamectl

**COPY**

**COPY**

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

## Pass is not initialized

```ruby
pass
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699277474918/0c4ced0d-8f23-4c1d-9327-8271cd530165.png align="center")

---

## **Generate a gpg key**

```ruby
gpg --generate-key
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699277538383/b7c142d7-aa7b-4f26-84af-529fcdb4cd9c.png align="center")

The `gpg --generate-key` command is used to generate a new GPG (GNU Privacy Guard) key pair.

GPG is a widely used open-source software for encrypting and signing data and is commonly used for securing email communications, verifying the authenticity of software packages, and protecting sensitive information.

---

## Provide information

Provide real name and email address

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699118803035/f5e2c0fb-5f1b-49e6-bf00-7be233615f70.png align="center")

---

## Choose a passphrase

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699277663452/ceda9e2a-c1ec-4d3c-8b32-4073c586ecf9.png align="center")

---

## Visualize your gpg key

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699118934427/1e58cbcd-4ce4-4d37-95c1-abeb828d4775.png align="center")

---

## List the keys

The following lists all the public keys

```plaintext
gpg --list-keys
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119146466/25700c0f-df68-48d6-843c-cea10dc53b37.png align="center")

Just in case you want to list all your private keys, you should run the following command:  
gpg --list-secret-keys

---

## Copy your public key

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119262142/5f45871a-d084-4ab4-8517-7ca24aaa49cf.png align="center")

---

## Initialize pass

```plaintext
pass init your-key
```

It should be something like the following:

```plaintext
pass init DAZF877093FCF01Z4BFA3A0256CD93F8BCFC51B4
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119385460/0ce003b2-a9da-4abe-afcd-73bcc04800ea.png align="center")

---

## Pass is initialized

```ruby
pass
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699277927634/9be72a83-522e-4dca-8b69-ec20afd3806b.png align="center")

---

## Open Docker Desktop

Click on sign-in

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119829149/0a21a8a7-b479-4135-8542-4ea87ba58eb4.png align="center")

---

## Login

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119888743/1b0d5f5f-8ccc-4c39-8041-d7bebfa7e814.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699119936035/d7375a7b-3677-4590-947b-bc816fab92fa.png align="center")

---

## Proceed to Docker Desktop

Click on `Open Docker Desktop URI handler`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699278074259/0a550bdb-9d29-4958-af9d-ec79b54dc239.png align="center")

---

## Logged in

Now, you should see your logged in.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699120067583/a9017574-2012-4e79-b74d-884fe67049e9.png align="center")

---

## **Done**

---

## **Celebrate**

![Happy Season 2 GIF by The Office - Find & Share on GIPHY](https://media2.giphy.com/media/jQediRqu0oLXNdjDbN/giphy.gif?cid=6c09b952sfrdnl666a3hp1aeryp278rp59g3w8aj33myfbux&ep=v1_internal_gif_by_id&rid=giphy.gif&ct=g align="left")

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