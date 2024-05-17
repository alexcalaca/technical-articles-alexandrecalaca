---
title: "How to show current git branch with colors in Bash prompt in Deepin OS and any other Debian based linux distributions"
datePublished: Sat Apr 29 2023 04:01:52 GMT+0000 (Coordinated Universal Time)
cuid: clh1ghps4000g09jq3ssk2u1m
slug: how-to-show-current-git-branch-with-colors-in-bash-prompt-in-deepin-os-and-any-other-debian-based-linux-distributions
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/H7LxvEmVZnE/upload/e68fb072027496a6f557019e66549971.jpeg
tags: ubuntu, programming-blogs, linux, programming-tips, vscode-extensions

---

#### Greeting

Hey guys. It's AC Alexandre Calaça here. How have you been?

---

#### Introduction

The goal of this article is to demonstrate how to include current git branch and path into bash prompt.

This article is tested in Debian based linux distributions.

---

#### Current environment

This is my current OS.

```apache
lsb_release -a
```

Output is something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682738551792/c1f32e4b-f7d9-4fa6-91f0-02f838a1f3f2.png align="center")

---

#### Open bash configuration

Open your file management tool and open `Home`. Press `CTRL+H` and open the file .bashrc.

---

#### Include the following commands

```apache
export PS1="\u@\h \[\e[32m\]\w \[\e[91m\]\$(parse_git_branch)\[\e[00m\]$ "
```

The previous command defines a new value for the environment variable PS1, which controls the format of the command prompt.

To be more specific, let's take a look at each part:

* `\u` expands to the username of the current user.
    
* `\h` expands to the hostname of the machine.
    
* `\[\e[32m\]` and `\[\e[91m\]` are ANSI escape sequences that set the text color to green and red, respectively.
    
* `\w` expands to the current working directory.
    
* `$(parse_git_branch)` is a command substitution that calls the `parse_git_branch` function to display the current Git branch name.
    
* `\[\e[00m\]` is an ANSI escape sequence that resets the text color to the default.
    

---

#### Test

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682739039880/0308d736-2988-4671-98c6-daf15de86fff.png align="center")

IT worked like a charm!!

---

#### Celebrate

![Michael Scott Excited GIFs | Tenor](https://media.tenor.com/j5uPfkaOQ98AAAAC/steve-carell-wow.gif align="left")

---

#### Summary

The article showed how to include current git branch and path into bash prompt in Deepin OS 20.7 and any other Debian based linux distributions.

---

#### Conclusion

That's all for today. Thanks for reading the article `How to show current git branch with colors in Bash prompt in Deepin OS and any other Debian based linux distributions.`

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.