---
title: "How to add environment variable assignments on Elementary OS 6.1 via the terminal emulator and the bash shell?"
datePublished: Fri Sep 15 2023 04:56:17 GMT+0000 (Coordinated Universal Time)
cuid: clmk4n3sn000009mi2kojh1q8
slug: how-to-add-environment-variable-assignments-on-elementary-os-61-via-the-terminal-emulator-and-the-bash-shell
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694753709529/b9da2b1a-2fd7-40cf-91eb-c21cd7357db6.jpeg
tags: tutorial, linux, elementary-os, environment-variables

---

---

## Environment variables

Environment variables are dynamic values that can affect the behavior of processes and programs running on a computer's operating system.

These variables store information such as system configuration settings, user preferences, or data that is used by various software applications.

Environment variables are used to control how programs behave and to provide them with necessary information.

---

## Open the terminal

```plaintext
CTRL + SHIFT + T
```

---

## Check your shell

```plaintext
echo $SHELL
```

My output is

```plaintext
/bin/bash
```

Your output might be one of the following:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694664358818/14b4030a-4bf0-41d8-8b2d-76afc2dbbe73.png align="center")

---

## Edit the shell configuration

Use your favorite text editor to edit the shell configuration file. I'm going to use `nano`. You can use nano, vi, vim, gedit and even VS Code.

```plaintext
nano ~/.bashrc
```

---

## Add the variables

In `~/.bashrc`, add the variables at the end:

```plaintext
export GITHUB_TOKEN="glpat-Z2hxZY6BhDPyZwQbYuZm"
export DOCKER_TOKEN="dckr_pat_ORhj8i17IaMZ8gvLMqZgdKnkD9Z"
export PG_USER="my_user"
export PG_PASS="d9l85nbp"
```

---

## Save the changes and exit

if you are using nano, follow the order:

* CTRL + X;
    
* Y and press Enter;
    

---

## Confirm the changes

```plaintext
source ~/.bashrc
```

---

## Check the changes

```plaintext
echo $GITLAB_TOKEN
echo $DOCKER_TOKEN
echo $PG_USER
echo $PG_PASS
```

---

## **Done**

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