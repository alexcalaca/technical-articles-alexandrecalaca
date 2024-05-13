---
title: "How to set a password for a user in Postgresql"
datePublished: Mon May 13 2024 16:22:06 GMT+0000 (Coordinated Universal Time)
cuid: clw569d24000808lcgkypdnuc
slug: how-to-set-a-password-for-a-user-in-postgresql
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/lRoX0shwjUQ/upload/2f19ac686b590b3ed14ee6b55569d6da.jpeg
tags: postgresql, terminal, alexandrecalaca

---

---

## Open a terminal

---

## Connect to Postgresql

```ruby
sudo -u postgres psql
```

`postgres` is the name of the user.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709692587506/09647aa3-be24-40c7-9794-fb375e33b92c.png?auto=compress,format&format=webp align="left")

---

## Change the password

```ruby
ALTER USER postgres WITH PASSWORD 'postgres';
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709695057074/b5274427-c14b-4635-8e83-668b46cabe8f.png align="center")

`'postgres'` is the password.

---

## Test the new password

```ruby
psql -U postgres -h localhost
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1709695192423/7359ef4e-87ec-445b-9111-f2f93dcf4c7b.png align="center")

---

## **Done**

---

### **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

### Reach me out

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**H**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ashnode**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

### Final thoughts

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!