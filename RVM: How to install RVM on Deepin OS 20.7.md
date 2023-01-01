# RVM: How to install RVM  on Deepin OS 20.7

Hey guys,
how have you been?

Today, we are  going to learn how to install `RVM` on Deepin OS 20.7, a Debian based distro.  
Actually, this procedure can be done in any Debian based distro.

### Introduction
`RVM` is a command-line tool that allows you to easily install, manage, and work with multiple ruby environments from interpreters to sets of gems. It was originally started in October of 2007.

Ruby Version Manager, often abbreviated as RVM, is a software platform for Unix-like operating systems designed to manage multiple installations of Ruby on the same device.


### 1 -  Update your system

Open the terminal and run the following command: 
```
sudo apt update && apt upgrade

```
### 2 - Install the required dependencies

```
sudo apt install apt-transport-https ca-certificates gnupg2 curl
```

### 3 - Import GPG Key
GPG stands for Gnu Privacy Guard and it is supported by the Internet Engineering Task Force ([IETF](https://www.ietf.org/)) through the [RFC 4880](https://www.ietf.org/rfc/rfc4880.txt).

The IETF publishes RFCs authored by network operators, engineers, and computer scientists to document methods, behaviors, research, or innovations applicable to the Internet.

GnuPG (more commonly known as GPG) is an implementation of a standard known as PGP (Pretty Good Privacy). It uses a system of "public" and "private" keys for the encryption and signing of messages or data.

```
curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -
``` 

### 4 - Install the RVM stable version


```
curl -sSL https://get.rvm.io | bash -s stable --ruby

```

By now, you should be able to see something like this:

![Screenshot_select-area_20221207231910.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670466689550/hvlEa0DXD.png align="left")

### 5 - Check RVM installation

```
rvm -v
```
You should be able to see something like this:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670466963635/e6JedBPz3.png align="left")

### 6 - List all Ruby versions available
```
rvm list known
```  

You should be able  to see something like this:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670467136561/oePiQQOwU.png align="left")

### 7 - Celebrate 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670467202120/39r84GZVW.png align="left")
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

### Conclusion
That`s all for today. I hope this article helped you. Let me know if you have any questions.



 
  
