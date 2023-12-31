---
title: "How to stage and commit only selected parts of a file"
datePublished: Sun Dec 31 2023 17:34:06 GMT+0000 (Coordinated Universal Time)
cuid: clqtrtt0c000408la0vve6cuu
slug: how-to-stage-and-commit-only-selected-parts-of-a-file
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Q9y3LRuuxmg/upload/c7553e64e60d580d72390c67c0af7df7.jpeg
tags: git, command-line, vscode, alexandrecalaca

---

---

## **Introduction**

Staging and committing different parts of a file can be useful in several scenarios, providing developers with more granular control over versioning and changes in their codebase.

Let me outline my 3 favorite reasons:

* **Separating Functional Changes:** If a single file contains changes related to multiple functionalities, you may want to commit each functionality separately. This can be beneficial for tracking and reverting changes related to specific features without affecting others.
    
* **Reverting Specific Changes:** If a file contains a mix of changes, and you later discover that one part introduces a bug, having granular commits makes it easier to revert only the problematic changes while keeping the rest of the modifications intact.
    
* **dressing Code Style Issues:** When cleaning up code or addressing code style issues, you might want to commit style changes separately from functional changes. This makes it easier to review and track improvements to code readability and maintainability.
    

---

## **Let's get down to business**

Shall we?

![It Crowd Brilliant Reaction Maurice Moss GIF | GIFDB.com](https://gifdb.com/images/high/it-crowd-brilliant-reaction-maurice-moss-dsk6k8go7wzin5p3.gif align="left")

---

## Current situation

Let's think about the following situation. I have changes in the `Menu` component and also in the `Footer` component.

My goal is to stage and commit them separately.

### Menu component

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703731403328/ebaa186e-38b1-4fb3-9b70-1cd8070b95da.png align="center")

---

### Footer component

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703731447386/7923a8aa-6819-4d9d-be02-1e9a3e0ffef5.png align="center")

---

### Approaches

There are two approaches to selectively commit specific parts of a file: one involves using terminal commands, while the other leverages the Visual Studio Code IDE.

Let's have a basic introduction of both and use them in my examples.

---

### **Terminal Command Line**

Utilizing the command line allows for a more direct and scriptable method of staging and committing changes. Developers can use Git commands, such as `git add -p` or `git add --patch` for interactive staging, to selectively choose chunks of changes to include in the commit.

This method is well-suited for those who prefer command-line interfaces and want fine-grained control over the staging process.

```plaintext
code# Example: Interactive staging using git add -p
git add --patch filename
git commit -m "Commit message"
```

---

### Visual Studio Code ide

Visual Studio Code provides a user-friendly and visual way to selectively stage changes within the IDE itself.

Developers can use the built-in Source Control view to hover over specific lines of code, stage them individually, and then commit only the selected changes. This method is beneficial for those who prefer a graphical interface and want a more intuitive way to manage their commits.

Basically, you select the file you want to commit. Select the line or part in the editor, right click button and choose `Stage selected ranges`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703820194043/458fde5f-3f3e-4c48-92d4-9f0e064f0819.png align="center")

Or just use the shortcut

```plaintext
CTRL + K
CTRL + ALT + S
```

---

## Get your hands dirty

### VS Code

Let's stage only the `Menu` component.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703820440102/de429b63-8bdb-4402-bcc5-c0051fdfb971.png align="center")

Let's select the desirable parts and right click on it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703820547607/4faa8f0d-bf89-446c-8486-bd8cf91c4ab1.png align="center")

---

### The terminal

Start with

```plaintext
git add -p src/index.js
```

Replace `src/index.js` with your filename.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703821026999/d973718a-97bb-40e2-9f62-c837fadd5841.png align="center")

Since the first part seems to be related to the `Menu` component. I'm going to say "No". I'm to say "Yes" in the last part

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703821132817/e37b7213-39f7-4440-bede-d63a36bc721b.png align="center")

---

## **Done**

---

## Conclusion

By following these steps, you can easily run RSpec tests within a Docker container without the need to modify Docker configurations.

This approach ensures consistent testing environments across different machines and simplifies the testing process for developers working with your Rails application.

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

## **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
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