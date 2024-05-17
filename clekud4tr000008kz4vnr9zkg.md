---
title: "Error: Validation failed: Image Failed to manipulate with MiniMagick, maybe it is not an image?"
datePublished: Sun Feb 26 2023 03:38:43 GMT+0000 (Coordinated Universal Time)
cuid: clekud4tr000008kz4vnr9zkg
slug: error-validation-failed-image-failed-to-manipulate-with-minimagick-maybe-it-is-not-an-image
tags: programming-blogs, ruby, ruby-on-rails, deepin

---

Hey guys, how have you been?

Today, we are going to learn how to solve the following error message:

```ruby
ActiveRecord::RecordInvalid (Validation failed: Image Failed to manipulate with MiniMagick, maybe it is not an image? Original Error: You must have ImageMagick or GraphicsMagick installed):
```

### Introduction

The error message happens when I try to save an uploaded file.

```ruby
ActiveRecord::RecordInvalid (Validation failed: Image Failed to manipulate with MiniMagick, maybe it is not an image? Original Error: You must have ImageMagick or GraphicsMagick installed)
```

Here's the snapshot of the server at the moment.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674669722769/defcf2ab-7575-4b1d-8335-c3f653435802.png align="center")

Here's the current Gemfile

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674669619697/c675752f-77c1-45a2-9ee2-0e90ef5efd01.png align="center")

My operating system is `Deepin OS 20.7.1`, a debian-based linux distribution.

You can check yours by running the following command:

```ruby
lsb_release -a
```

#### **1 - Repair broken dependencies**

The `-f, --fix-broken` option attempts to correct a system with broken dependencies in place.

This option, when used with `install/remove`, can omit any packages to permit APT to deduce a likely solution. If packages are specified, these have to completely correct the problem.

Run the following command:

```ruby
sudo apt --fix-broken install
```

You should be able to see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677378969390/6945e6a6-699a-454d-b11c-bf4fd5871c18.png align="center")

---

#### 2 - Install ImageMagick

```ruby
sudo apt-get install imagemagick
```

You should get something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677377950014/784ed6ff-3ab1-45fb-8622-885508725454.png align="center")

...

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677377984975/8ee457fc-cbb4-4160-b68e-02812ee3fbdf.png align="center")

---

#### 3 - Check if it's installed

```ruby
identify -version
```

You should see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677378161170/c1ee7f22-3bc9-4c82-835d-3f92b0923a58.png align="center")

---

#### 4 - Test it again

---

#### 5 - Celebrate

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif align="center")

### Conclusion

That's all for today. I hope this article helped you.

Let me know if you need any additional help.