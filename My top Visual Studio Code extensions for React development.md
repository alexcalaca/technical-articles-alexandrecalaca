---
title: "My top Visual Studio Code extensions  for React development"
datePublished: Sat Oct 21 2023 19:56:56 GMT+0000 (Coordinated Universal Time)
cuid: clo0go0n800050amo6w1vbhe5
slug: my-top-visual-studio-code-extensions-for-react-development
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697918141937/eb00d067-b795-4a7f-ac66-0f17aff0e2c5.jpeg
tags: software-development, web-development, reactjs, frontend-development, vscode

---

---

## React.js

`React`, also known as React.js or ReactJS, is an open-source JavaScript library for building user interfaces (UIs) and web applications.

Developed and maintained by Facebook, React has gained widespread popularity in the web development community for its efficiency, flexibility, and component-based architecture.

---

## Note

My articles are constantly evolving, and I welcome any feedback, corrections, broken links, or suggestions you may have. Please don't hesitate to share them with me, and I'll be grateful for your input.

Give me a shout or add me:

* [**Github**](https://github.com/elitebughunter)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Let's get down to business**

shall we?

![The-office GIFs - Get the best GIF on GIPHY](https://media1.giphy.com/media/BpGWitbFZflfSUYuZ9/giphy.gif align="left")

---

---

## Make sure you VS Code

In [this article](https://blog.alexandrecalaca.com/how-to-install-visual-studio-code-on-linux-mint-21-vanessa-or-any-other-ubuntu-based-linux-distribution-with-a-debian-file-format), you can check its installation process with a Debian file format. [Check it out](https://blog.alexandrecalaca.com/how-to-install-visual-studio-code-on-linux-mint-21-vanessa-or-any-other-ubuntu-based-linux-distribution-with-a-debian-file-format).

On Fedora, it's [this article](https://blog.alexandrecalaca.com/how-to-install-vs-code-on-fedora-38-a-step-by-step-guide).

---

## Open a terminal

```ruby
CTRL + ALT + T
```

---

## ESLint

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696183393128/bb3acf6d-966d-43dc-8803-f3c9e975420a.png align="center")

The extension uses the ESLint library installed in the opened workspace folder. If the folder doesn't provide one the extension looks for a global install version.

```ruby
code --install-extension dbaeumer.vscode-eslint
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696132437089/f8d1c666-3dfb-43e4-829d-f51f6edd4084.png align="center")

---

### Configure it on save

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696182825945/bb4dc52e-7543-448c-8651-013eb9d5d724.png align="center")

---

## Prettier - Code formatter

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696183434258/6d971b66-4090-42b3-ab6b-7f15ea09209d.png align="center")

[Prettier](https://prettier.io/) is an opinionated code formatter. It enforces a consistent style by parsing your code and re-printing it with its own rules that take the maximum line length into account, wrapping code when necessary.

```ruby
code --install-extension esbenp.prettier-vscode
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696132720197/ecf2a5df-724e-4020-82cd-43598724338d.png align="center")

---

### Set as default formatter

Configure `Prettier - Code formatter` as our VS Code default.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696182475627/feb4e4b1-96f0-4004-985b-f0aee208e46b.png align="center")

---

## Npm intelissense

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696183470760/fa0263d9-e2e1-4c1d-ba23-83fc5a34ddc6.png align="center")

Visual Studio Code plugin that autocompletes npm modules in import statements.

![auto complete](https://github.com/ChristianKohler/NpmIntellisense/raw/HEAD/images/auto_complete.gif align="left")

```ruby
code --install-extension christian-kohler.npm-intellisense
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696133472621/7acc82df-6138-46a7-a441-13e3a581dad0.png align="center")

---

## **VSCode React refactor**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696183499795/846532ce-b43e-4e71-8761-69799b662f3c.png align="center")

This simple extension provides JSX refactor code actions for React developers.

## Features

* Extract JSX code parts to a new class or functional component
    
* Supports TypeScript and TSX
    
* Works with classes, functions and arrow functions
    
* Handles key attribute and function bindings
    
* Compatible with React Hooks API
    

## Preview

![preview](https://github.com/planbcoding/vscode-react-refactor/raw/master/assets/images/preview.gif align="left")

```plaintext
code --install-extension planbcoding.vscode-react-refactor
```

---

## Material Icon Theme

Files and folder icons for Visual Studio Code. The repo can be found [here](https://github.com/PKief/vscode-material-icon-theme)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696183580764/0d1a176e-7d40-4076-bff0-cad690980129.png align="center")

```ruby
code --install-extension pkief.material-icon-theme
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696180693200/288e6891-11fb-40db-8db5-1c21d7e9bdd6.png align="center")

---

## Auto REname TAG

Automatically rename paired HTML/XML tag, same as Visual Studio IDE does. The repo can be found [here](https://github.com/formulahendry/vscode-auto-rename-tag).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696183649993/661b22f5-981e-4b3d-a2d3-dae2316b3c11.png align="center")

```ruby
code --install-extension formulahendry.auto-rename-tag
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696181033607/b26ecdd1-2e5b-453e-b74c-f0e15ddace07.png align="center")

---

## Code Snap

It allows us to take beautiful screenshots of the code.

Main Features:

* Quickly save screenshots of your code;
    
* Copy screenshots to your clipboard;
    
* Show line numbers
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696181262418/011a65cd-25e5-4438-a534-1bdba8aecfc2.png align="center")

```ruby

code --install-extension robertz.code-snapshot
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696181245188/e879a168-a1ec-477a-860b-0daa5c3b32dd.png align="center")

---

# **Import Cost**

This extension will display inline in the editor the size of the imported package. The extension utilizes webpack in order to detect the imported size.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696181399289/3e196e73-c25b-4535-a0ff-205744554534.png align="center")

```ruby
code --install-extension wix.vscode-import-cost
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696181463956/0632a6b1-f083-4cf9-8829-49bc5c5aeef6.png align="center")

---

## Check all extensions installed

```ruby
code --list-extensions
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697917933463/3dad2fa9-5fd3-4749-802c-c45fc439676d.png align="center")

---

## Done

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

Feel free to suggest topics for future blog articles. Until next time!

---
