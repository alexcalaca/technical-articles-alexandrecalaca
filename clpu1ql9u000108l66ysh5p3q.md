---
title: "Step-by-step guide to setting up Ruby with Rbenv on Pop!_OS 22.04"
datePublished: Wed Dec 06 2023 17:31:49 GMT+0000 (Coordinated Universal Time)
cuid: clpu1ql9u000108l66ysh5p3q
slug: step-by-step-guide-to-setting-up-ruby-with-rbenv-on-popos-2204
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701883706914/cfd2f282-2054-4e77-bb5e-85536a3d0027.png
tags: ubuntu, ruby, ruby-on-rails, popos, alexandrecalaca

---

---

## Rbenv

`rbenv` is a lightweight Ruby version management tool. It allows you to easily install, manage, and switch between different versions of Ruby on your system.

This is particularly useful for developers who may need to work on projects that require different Ruby versions or need to keep their development environment in sync with specific Ruby versions.

With rbenv, you can set a Ruby version on a per-project basis, ensuring that each project uses the appropriate version of Ruby.

This helps in avoiding conflicts between projects that might require different Ruby versions and ensures consistency across your development environment.

---

## Update your OS

```plaintext
sudo apt update
```

---

## Install the dependencies

```plaintext
sudo apt install git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev
```

---

## Install rbenv

```plaintext
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701882331098/0bcb7ba7-5a03-44df-bafb-67603a03961f.png align="center")

---

## Add rbenv to $PATH

```plaintext
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701882525621/4a63c8a3-2e69-48ed-a15d-dbc22b63eb81.png align="center")

---

## Load rbenv

```plaintext
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701882520822/c123b59b-4632-4b80-a55a-8459a5349eb6.png align="center")

---

## Apply changes to current session

```plaintext
source ~/.bashrc
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701882516662/92759804-e936-41df-b925-0ae422f03039.png align="center")

---

## Verify installation

```plaintext
type rbenv
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701882507513/0fba5b85-2cd8-4bce-9d17-cf586023eda9.png align="center")

---

## List all possible Ruby versions

```plaintext
rbenv install --list-all
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701882745807/965ad97c-85c2-486e-aa29-d696f1654753.png align="center")

---

## Install ruby

```plaintext
rbenv install 2.6.3
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701883258010/308f615c-81b4-4d87-9fa0-b4cbef37728b.png align="center")

---

## Set default version

```plaintext
rbenv global 2.6.3
ruby -v
```

---

## Done

---

## Celebrate

Well-done. You did a great job!

![Casts Of The Office Celebration Dance GIF | GIFDB.com](https://gifdb.com/images/high/casts-of-the-office-celebration-dance-p9rrkj7pyawhjo54.gif align="left")

---

## **Let's network**

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