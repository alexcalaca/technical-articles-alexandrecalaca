---
title: "How to create a Git commit without a message?"
datePublished: Thu Sep 25 2025 03:17:40 GMT+0000 (Coordinated Universal Time)
cuid: cmfyuehx8000002ld9vfbhhw6
slug: how-to-create-a-git-commit-without-a-message
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/KPAQpJYzH0Y/upload/cacf4b3b9e2597230868eb5f3db92ea9.jpeg
tags: github, git, alexandrecalaca

---

### Solution

Here it is:

```plaintext
git commit --allow-empty-message -m ""
```

### Explanation

To create a Git commit without a message, or with an empty message, you can use the `--allow-empty-message` flag with the `git commit` command.

```plaintext
git commit --allow-empty-message -m ""
```

Breaking it down:

* `git commit`: This is the standard command for creating a new commit.
    
* `--allow-empty-message`: This flag explicitly tells Git to allow a commit with an empty message.
    
* `-m ""`: This specifies an empty commit message. You must still include the `-m` flag, even if the message content is an empty string.
    

---

### Done

---