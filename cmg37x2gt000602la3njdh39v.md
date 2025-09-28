---
title: "From Github Codespaces to Repository: Step-by-Step Setup"
datePublished: Sun Sep 28 2025 04:47:06 GMT+0000 (Coordinated Universal Time)
cuid: cmg37x2gt000602la3njdh39v
slug: from-github-codespaces-to-repository-step-by-step-setup
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/HLQDfaJUTVI/upload/4e35957731362ea8f7545c611581a9a0.jpeg
tags: github, alexandrecalaca

---

## Introduction

### Context

By default, Codespace is using the `GITHUB_TOKEN` env var (the “Codespaces token”), which **can’t create repos**.

It’s necessary to authenticate `gh` with a token/account that has the right scopes, or create the repo on the web first.

### Objective

In this article, let’s focus on authenticating, setting the right scopes and creating the repo.

---

## Solution

### Initiate the project

In short: we’ll check status → create repo → stage everything → commit it.

```plaintext
git status || git init
git add .
git commit -m "init"
```

git status → shows the current state of the repository (which files are changed, staged, or untracked).

git init → initializes a new Git repository in the current folder.

git add . → stages all changes (new, modified, deleted files) in the current folder for the next commit.

git commit -m "init" → creates a commit with the message "init".  

---

### Check the environment

In short: we’ll log out of the GitHub CLI, then clear the token stored in our environment.

```plaintext
gh auth logout -h github.com
unset GITHUB_TOKEN
```

* `gh auth logout -h` [`github.com`](http://github.com) → logs you out from GitHub CLI (`gh`) specifically for the host [`github.com`](http://github.com).
    
* `unset GITHUB_TOKEN` → removes the `GITHUB_TOKEN` environment variable from your current shell session.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1759032974457/2bb5c737-bcbe-4590-b32e-afe099af6933.png align="center")

---

### Login

In short: you log in via browser, then check if the login worked.

```plaintext
gh auth login -h github.com -p https -w
gh auth status
```

* `gh auth login -h` [`github.com`](http://github.com) `-p https -w` → logs you in to GitHub CLI (`gh`) for the host [`github.com`](http://github.com), using HTTPS as the protocol (`-p https`), and opens a web browser (`-w`) to complete the authentication.
    
* `gh auth status` → shows your current GitHub CLI authentication status (which account you’re logged in with, token details, active host, etc.).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1759032974457/2bb5c737-bcbe-4590-b32e-afe099af6933.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1759033155166/43ab4a71-003c-44ea-8e4c-ac5b667a0fac.png align="center")

---

### Double check login

```plaintext

gh auth status
gh api user
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1759034659039/4c31e951-f521-4e5f-9170-a7c9b5449dcf.png align="center")

---

---

### Create and push

In short: this creates a new private repo on GitHub and immediately pushes your local project there.

```plaintext
gh repo create alexcalaca/profile-card --private --source . -
-remote origin --push
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1759033345675/5e7d6a90-7fe1-40e4-91d8-45bc91cd3977.png align="center")

---

## Done

---