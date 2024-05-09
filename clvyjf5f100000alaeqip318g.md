---
title: "How to uninstall Ruby completely from Linux Mint"
datePublished: Thu May 09 2024 00:56:07 GMT+0000 (Coordinated Universal Time)
cuid: clvyjf5f100000alaeqip318g
slug: how-to-uninstall-ruby-completely-from-linux-mint
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/VKLJ-BJlszE/upload/4ad703fb8893a901881248fbbe716f7d.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

---

## Ruby

Ruby is a dynamic, object-oriented programming language known for its simplicity and productivity.

It was created in the mid-1990s by Yukihiro Matsumoto (often referred to as "Matz") in Japan. Ruby is designed to be both powerful and easy to read and write, with syntax inspired by Perl and Smalltalk.

---

## Removal

### Remove Ruby packages

```ruby
sudo apt remove ruby ruby-dev ruby-full
```

Let's uninstall any Ruby packages that were installed via the package manager.

Open a terminal and run the previous command to uninstall Ruby and related packages.

This command removes the Ruby interpreter, development headers, and any additional Ruby packages that were installed.

---

### Remove Ruby Gems (optional)

```ruby
sudo gem uninstall --all
```

---

### Remove Ruby-related directories

Ruby installations may leave behind some directories or configuration files.

Let's manually remove these directories if they exist:

```ruby
rm -rf ~/.gem
rm -rf /usr/local/lib/ruby
```

---

### Check for any remaining Ruby-related files

You can use the find command to search for any remaining files related to Ruby:

```ruby
sudo find / -name "*ruby*" -or -name "*gem*"
```

This command searches the entire filesystem for files and directories containing "ruby" or "gem" in their names.

Review the output and delete any remaining files or directories that are related to Ruby.

---

## **Done**

---

### Verify removal

```ruby
ruby -v
```

If Ruby has been successfully removed, you should see a message indicating that the command is not found.

---

### Celebrate

Well-done. You did a great job!

![Casts Of The Office Celebration Dance GIF | GIFDB.com](https://gifdb.com/images/high/casts-of-the-office-celebration-dance-p9rrkj7pyawhjo54.gif align="left")

---

### **Let's network**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!

---