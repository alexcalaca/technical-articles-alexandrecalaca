---
title: "How to configure and use a dedicated SSH Key in a Bitbucket  project?"
datePublished: Tue Sep 05 2023 03:43:32 GMT+0000 (Coordinated Universal Time)
cuid: clm5rn1az000708my28xognge
slug: how-to-configure-and-use-a-dedicated-ssh-key-in-a-bitbucket-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693885366928/f318c958-ebe9-4a1b-9070-9ea1f8866668.png
tags: ubuntu, linux, git, bitbucket, deepin

---

---

### SSH

SSH stands for "Secure Shell." It is a cryptographic network protocol used to securely access and manage network devices and servers over a potentially unsecured network.

SSH provides a secure way to establish a remote connection to a system, allowing users to execute commands and manage files on a remote machine as if they were physically present at the computer.

---

### Requirements

You need to have an SSH key added to your Bitbucket project.

---

### Solution

---

### List all SSH keys

```apache
ls ~/.ssh/
```

Output

```apache
calaca@calaca-PC ~/var/www $ ls ~/.ssh/
config  id_ed25519  id_ed25519.pub  known_hosts  ssh_key_adc  ssh_key_adc.pub
```

---

### Check the content

Select the desired SSH key and review its contents.

```apache
cat ~/.ssh/ssh_key_adc.pub
```

Output

```apache
calaca@calaca-PC ~ $ cat ~/.ssh/ssh_key_adc.pub
ssh-ed25519 ABADC3NzaC1l0DI1NTE5AAAAIMWf5MaychLIR0mbAvXfpy9IPvrczLr55WTZUu3Tqad email@myemail.com
```

---

### Create a SSH config file

```apache
touch ~/.ssh/config
```

---

### Understand the configuration

In this step, we'll use the Bitbucket project clone link. In my example, I'll use the following clone link

```plaintext
git@bitbucket.org:my_organization_name/my_app.git
```

---

### Open the SSH config file

```plaintext
code ~/.ssh/config
```

I used `VS Code Studio` to open it, however, you can use your favorite text editor.

---

## Configure the SSH Key config file

Basically, the ssh key `config` file has 03 components: `Host`, `HostName` and `IdentifyFile`.

Let's start with the easiest: `HostName`.

---

### HostName

Since we're configuring Bitbucket, our `HostName` is the following:

```plaintext
HostName bitbucket.org
```

The previous and the following code snippets must be inside the `~/.ssh/config` file.

---

### IdentifyFile

Here, we're going to insert the path of our private ssh key.

```plaintext
IdentityFile ~/.ssh/ssh_key_adc
```

So far, we have the following code inside the `~/.ssh/config` file.

```plaintext
HostName bitbucket.org
IdentityFile ~/.ssh/ssh_key_adc
```

---

### Host

The `Host` can be virtually anything you want, but I recommend using something like the following:

```apache
Host bitbucket.org-work_adc
```

When you use SSH to connect to a remote server, you typically use the server's domain name or IP address.

However, with this configuration, you're creating an alias for the host configuration that you can use in your SSH commands.

So far, our code looks something like the following:

```apache
Host bitbucket.org-work_adc
    HostName bitbucket.org
    IdentityFile ~/.ssh/ssh_key_adc
```

---

### Review SSH config file

The following is the complete code:

```apache
Host bitbucket.org-work_adc
    HostName bitbucket.org
    IdentityFile ~/.ssh/ssh_key_adc
```

---

## Modify the clone link

A bitbucket clone link looks like the following:

```plaintext
git@bitbucket.org:my_organization_name/my_app.git
```

In order to use our ssh key, we'll have to change that link slightly based on the `Host` info. The new link would be like the following:

```plaintext
git@bitbucket.org-work_adc:my_organization_name/my_app.git
```

The reason for the change is due to the content of the `~/.ssh/config` file:

```plaintext
Host bitbucket.org-work_adc
    HostName bitbucket.org
    IdentityFile ~/.ssh/ssh_key_adc
```

With this configuration, you're creating an alias for the host configuration that you can use in your SSH commands.

Let's modify the bitbucket clone link in order to apply that, the new bitbucket clone link is going to be:

```plaintext
git@bitbucket.org-work_adc:my_organization_name/my_app.git
```

---

## Clone the project

```plaintext
git clone git@bitbucket.org-work_adc:my_organization_name/my_app.git
```

---

### Open the folder's project

In my example

```plaintext
cd var/www/my_project_name
```

---

## Check user associated with repo

```plaintext
git config --list
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693860269247/3ab0f519-1b08-4687-9719-c0cab1507b22.png align="center")

---

## Being more specific about the user

```plaintext
git config --list --local
```

The command `git config --list --local` is used to display the Git configuration settings for the current Git repository at the local level. It specifically lists the configuration settings that are specific to the repository where you run the command.

---

## Remove user associated with repo

```plaintext
git config --local --unset user.email
git config --local --unset user.name
```

---

## Add new user

```plaintext
git config --local user.name "My new name"
git config --local user.email "my-new-email@email.com"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693860456225/72e8678e-df2f-4563-952c-90027aed5a9f.png align="center")

---

## Check repo info

```plaintext
git config --list --local
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693861159276/86eab509-7034-463e-b459-72b662386bcc.png align="center")

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

I look forward to seeing you next time

---
