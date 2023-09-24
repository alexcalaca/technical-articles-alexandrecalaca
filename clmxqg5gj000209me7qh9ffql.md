---
title: "How to log in automatically to bash in the Terminator terminal emulator on Deepin OS 20.9?"
datePublished: Sun Sep 24 2023 17:27:44 GMT+0000 (Coordinated Universal Time)
cuid: clmxqg5gj000209me7qh9ffql
slug: how-to-log-in-automatically-to-bash-in-the-terminator-terminal-emulator-on-deepin-os-209
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695576423267/0948c544-2a6c-424b-b794-446d7e6816ca.png
tags: tutorial, ubuntu, linux, bash, debian

---

---

## Login shell

A `login shell` is a type of shell session that is typically used when you log in to your system. It executes certain initialization files and scripts, such as `.bash_profile`, `.bashrc`, or equivalent files for other shells like `.zshrc` for Zsh.

These files can contain environment variable definitions, path configurations, and other settings that should be applied globally to your user session.

---

### Main pro

Your user experience goes to a different level when it comes to automatic login.

Automatic login can save time and effort, especially if you use the same terminal configuration and working directory for every session.

You won't need to manually start the shell or navigate to your preferred directory each time you open a terminal.

---

### Main con

Automatic login bypasses the need to enter your password or use other forms of authentication. This can be problematic if you're relying on your user account's password for security.

If your system is compromised, an attacker can gain access to your user account without needing to know your password.

---

## Solution

![Get It Done Command GIF - Get It Done Command Finish It - Discover & Share  GIFs](https://media.tenor.com/PYQ2dEPFEL4AAAAC/get-it-done-command.gif align="center")

---

## Check your OS

This step is just to make sure you have **Deepin OS 20.9** installed.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
```

---

## Open the terminal

```apache
CTRL + ALT + T
```

---

## Open Preferences

Right-click on the terminal and choose `Open Preferences`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695525261107/d6d4811c-78d7-45cd-b2be-123ebf230a20.png align="center")

---

## Profiles

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695525312137/26ea3f03-794b-4b1d-8b6f-cffc2e668192.png align="center")

  
In the `Terminator` terminal emulator, profiles are configurations that allow you to customize the appearance and behavior of your terminal sessions.

Profiles enable you to create different settings for different terminal windows or tabs, making it easier to manage and organize your work environment.

---

## Command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695525377192/f87e12d4-be97-46ef-b193-6bd4b43268d7.png align="center")

---

## Run command as login shell

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695525460602/8acde3ac-38a1-43d0-b142-2c30ebbbd29c.png align="center")

When you enable the option in your Terminator profile settings and open a new terminal window or tab with that profile, `Terminator` will start a new shell session as a login shell.

This means it will execute the login shell's initialization files, allowing you to set global environment variables and apply system-wide configurations.

---

## Confirm

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695525637931/2d0ca9f2-ddd8-428e-b241-e2c143e207bb.png align="center")

---

### **Restart your terminal**

---

## Done

---

### **Celebrate**

![Gifs de the office - Gifs e Imagens Animadas](https://gifs.eco.br/wp-content/uploads/2022/06/gifs-de-the-office-0.gif align="center")

---

### **Let's connect**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### **Final thoughts**

I hope this article has been helpful to you. Please feel free to ask if you have any questions.

Your thoughts, suggestions, and corrections are highly welcome.

By the way, don't hesitate to share your ideas for new blog articles. Looking forward to seeing you next time.

---