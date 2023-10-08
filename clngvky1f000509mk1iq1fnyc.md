---
title: "Creating a react app with CRA (Create React App) on Deepin Linux 20.9 apricot via the command-line"
datePublished: Sun Oct 08 2023 02:59:03 GMT+0000 (Coordinated Universal Time)
cuid: clngvky1f000509mk1iq1fnyc
slug: creating-a-react-app-with-cra-create-react-app-on-deepin-linux-209-apricot-via-the-command-line
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/3bc8c6a454fa3037696ea2677e66fe85.jpeg
tags: javascript, web-development, reactjs, deepin

---

## React.js

`React`, also known as React.js or ReactJS, is an open-source JavaScript library for building user interfaces (UIs) and web applications.

Developed and maintained by Facebook, React has gained widespread popularity in the web development community for its efficiency, flexibility, and component-based architecture.

---

## Note

My articles are constantly evolving, and I welcome any feedback, corrections, or suggestions you may have. Please don't hesitate to share them with me, and I'll be grateful for your input.

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

## Check your OS

This step is just to make sure you have **Linux Mint** or a \*\*Ubuntu-\*\*based Linux distribution.

```ruby
cat /etc/os-release
lsb_release -a
uname -a
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696732362459/4c2bd868-1572-49d4-8cf2-5620950290cc.png?auto=compress,format&format=webp align="left")

---

## Install Google Chrome

In [this article](https://blog.alexandrecalaca.com/deepin-os-how-to-install-google-chrome-on-deepin-os-207), you can check its installation process with wget and a Debian file format. [Check it out](https://blog.alexandrecalaca.com/deepin-os-how-to-install-google-chrome-on-deepin-os-207).

---

## Install Node.js

In [this article](https://blog.alexandrecalaca.com/installing-nodejs-with-nvm-on-deepin-209-apricot-or-debian-based-distros), you can check its installation process with `curl` and `nvm`. [Check it out](https://blog.alexandrecalaca.com/installing-nodejs-with-nvm-on-deepin-209-apricot-or-debian-based-distros)[.](https://blog.alexandrecalaca.com/installing-nodejs-with-nvm-on-linux-mint-21-vanessa-or-ubuntu-based-distros)

---

## Install CRA

```ruby
npm install -g create-react-app
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696733714340/f6fde1d5-27ab-42a3-8d74-bfdb62e30e05.png align="center")

**Create React App (CRA)** is an official command-line tool provided by the React team and the Facebook development community. It simplifies the process of setting up and bootstrapping new React.js applications.

CRA generates a complete and well-structured React project with all the essential files, configurations, and development tools preconfigured, allowing developers to start building React applications quickly without the need to manually set up the project structure.

---

## Create react app

```ruby
npx create-react-app my-react-app
```

Replace `my-react-app` with your actual app's name.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696129141298/e2a087eb-12e0-4c98-80a0-94919e48252b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696129167319/29ee944f-82bd-4f4b-9ffb-4aa8c1fb3655.png align="center")

The command `npx` is used instead of `npm` when creating a new React project with Create React App (CRA) because npx is a package runner tool that comes with npm (Node Package Manager) and is designed to make it easier to run packages that are not globally installed on your system.

In summary, the use of `npx` when creating React projects with CRA is a best practice that leverages the ability to run packages without global installations, making it easier to manage and use tools like Create React App while avoiding potential version conflicts.

---

## Navigate to the project folder

```ruby
cd my-react-app/
```

---

## Start the development server

```ruby
npm start
```

In order to start the development server and run your React application locally, use the previous command.

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696129553292/d45313b1-3408-434d-9783-12009a34feb4.png align="center")

---

## Check the up-and-running page

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696129590404/d0476d6c-5ec5-4e95-94cd-001e4c6432fc.png align="center")

---

## Stop the server (optional)

In order to finish, just press:

```ruby
CTRL + C
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696129630394/bb0e6c3a-c5bb-4c97-8c0c-81e6e8dfb1b7.png align="center")

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