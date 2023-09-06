---
title: "Error @babel/plugin-proposal-private-property-in-object without declaring it in its
dependencies (or devDependencies) in the package.json file"
datePublished: Wed Sep 06 2023 10:59:20 GMT+0000 (Coordinated Universal Time)
cuid: clm7mnbpg000e09l25hz59ffy
slug: error-babelplugin-proposal-private-property-in-object-without-declaring-it-in-its-dependencies-or-devdependencies-in-the-packagejson-file
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693997862218/c5b93150-81dd-4fdb-8f31-90b8a548a077.png
tags: javascript, web-development, ruby-on-rails

---

---

## Error

```apache
Error: [BABEL]: --- PLACEHOLDER PACKAGE ---
This @babel/plugin-proposal-private-property-in-object version is not meant to
be imported. Something is importing
@babel/plugin-proposal-private-property-in-object without declaring it in its
dependencies (or devDependencies) in the package.json file.
Add "@babel/plugin-proposal-private-property-in-object" to your devDependencies
to work around this error. This will make this message go away.
```

---

### Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693947189396/af3bc378-b90a-447f-b715-5758380d570d.png align="center")

---

## Context

The error happens when it runs `rails server` in a Ruby on Rails 6 application.

---

## Current configuration

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693947295779/5af27df8-90f5-4553-870d-d5e4b600ffbb.png align="center")

---

## Solution

In the terminal:

```apache
npm install --save-dev @babel/plugin-proposal-private-property-in-object
```

The command `npm install --save-dev @babel/plugin-proposal-private-property-in-object` is used to install the Babel plugin `@babel/plugin-proposal-private-property-in-object` as a development dependency in a Node.js project.

Babel is a popular JavaScript compiler used for transpiling modern JavaScript code into an older version of JavaScript that is compatible with a wider range of browsers.

---

### Solution explanation

Here's what the `@babel/plugin-proposal-private-property-in-object` plugin does and why you might use it:

* Private class properties
    

In JavaScript, class properties are typically public, meaning they can be accessed and modified from outside the class. However, there is a proposal in JavaScript to support private class properties, which are properties that can only be accessed and modified from within the class where they are defined. These private properties are denoted by a `#` symbol before the property name.

---

* **Babel Plugin**:
    

The `@babel/plugin-proposal-private-property-in-object` plugin is a Babel plugin that allows you to use private class properties syntax in your JavaScript code, even if it's not natively supported by the JavaScript runtime in your target environment.

---

* **Transpilation**
    

When you use this Babel plugin, it transpiles your JavaScript code that contains private class properties into equivalent code that can run in environments that don't yet support private class properties natively. It essentially converts your code into a form that is compatible with older browsers or environments.

---

* **Development Dependency**
    

You install this plugin as a development dependency (`--save-dev`) because it's primarily used during the development and build process, not at runtime. It's part of your build toolchain, and it helps ensure your code can be executed in a wider range of environments when you bundle and deploy your application.

---

## **Stop the server**

In order to stop the `Rails Server`, let's press the following command:

```apache
CTRL + C
```

---

## Restart the server

```apache
rails server
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693944348977/dc8117f5-2935-45e9-a2a0-ec4ca2d1e5a5.png?auto=compress,format&format=webp align="left")

---

## Access a specific page

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693947546363/58796939-644c-4769-a3ec-47cd43612e23.png?auto=compress,format&format=webp align="left")

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