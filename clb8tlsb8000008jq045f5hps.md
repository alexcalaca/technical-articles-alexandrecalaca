# Deepin OS: How to install Google Chrome on Deepin OS 20.7

Hey guys, how have you been?

Today, we are  going to learn how to install `Google Chrome` on Deepin OS 20.7, a Debian based distro.  

#### Introduction
`Google Chrome browser` was first publicly released, officially as a beta version, on September 2, 2008, for Windows XP and newer, and with support for 43 languages, and later as a "stable" public release on December 11, 2008.

The idea was to innovate the web and the browser was built on the existing technologies. The Google chrome was developed keeping in mind to build something more than a browser and so it was developed with a lot of web applications in mind

#### 1 -  Update your system

Open the terminal and run the following command: 
```
sudo apt update

```
#### 2 - Install `wget` utility tool

`wget` is a free GNU command-line utility tool used to download files from the internet. It supports HTTP, HTTPS, and FTP protocols.

`wget` has been designed for robustness over slow or unstable network connections; if a download fails due to a network problem, it will keep retrying until the whole file has been retrieved.

It is capable of downloading multiple files, resuming downloads and even mirroring a remote site.


```
sudo apt -y install wget

``` 

#### 3 - Download the .deb package
`.deb` is the format, as well as extension of the software package format for the Debian Linux distribution and its derivatives.

So, deb is an abbreviation for Debian package, as opposed to source package.

```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb 

``` 

So far, this is the output.

![Screenshot_deepin-terminal_20221203212900.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670124404399/q4Ipkij9D.png align="left")

#### 4 - Install Google Chrome Browser on Deepin Linux 20.7

```
sudo apt install ./google-chrome-stable_current_amd64.deb
```
#### 5 - Launch Google Chrome
On terminal, run the  following command:


```
google-chrome
```

#### 6 - Celebrate 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670125312642/Mk2RfkJIJ.png align="left")

#### Conclusion
That`s all for today. I hope this article helped you. Let me know if you have any questions.



 
  
