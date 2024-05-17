---
title: "How to install AWS CLI on PopOs"
datePublished: Fri May 17 2024 13:41:46 GMT+0000 (Coordinated Universal Time)
cuid: clwaqalau00000ame3zoq8z2q
slug: how-to-install-aws-cli-on-popos
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715953260070/79a032c8-5e0f-4647-8b1e-5b8b7372fb9d.png
tags: linux, aws, popos, alexandrecalaca

---

---

## Access the website

Go to [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/) or [click here](https://aws.amazon.com/cli/).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715951944109/cd6616e3-f55c-47a8-9620-fcf48f662d84.png align="center")

---

### Download the Linux installer

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715951969879/cb1420a7-127b-4c8b-9c11-9e54e329983c.png align="center")

Another option is to click directly on this link: [https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#cliv2-linux-install](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#cliv2-linux-install).

---

### Choose Linux

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715952115249/0d1f9d69-e5b6-4717-b27b-165a1683ad29.png align="center")

---

## Install

Execute the following command in a terminal:

```ruby
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

These commands are used to download the AWS CLI executable for Linux, extract it from the downloaded ZIP file, and then install it using the provided installation script with elevated privileges.  

Installation in progress

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715952389125/16622955-b1e4-477f-96e0-6d1824453081.png align="center")

---

### Confirm installation

#### Version

```ruby
/usr/local/bin/aws --version
```

#### Executable

```ruby
which aws
```

  
Post-run after installation

```ruby
aws
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715952595990/ade2e910-ff89-49ac-8b6f-59013c502d3d.png align="center")

---

## **Done**

---

### Conclusion

By following these steps, you can easily visualize how the installation of AWS Cli works.

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### **Reach me out**

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