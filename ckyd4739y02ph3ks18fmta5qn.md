## How to install Anydesk (remote desktop software) on Ubuntu

### Introduction
The goal of this article is to show how to install Anydesk on Ubuntu.

### Steps to install Anydesk

Step 1. Open the terminal
Step 2. Check if you system is 32 or 64 bits
```
uname -m
```

The result:
- 64 bits: `x86_64`;
- 32 bits: `i386`, `i486`, `i586`, `i686` or something like this.

Step 3. Download it from the website through this  [link](https://anydesk.com/en/downloads/linux) or  [click here](https://anydesk.com/en/downloads/linux).

Name it as **anydesk.deb**.

Instead of downloading it, If you prefer, you can also run one of the following commands:
- System is 32 bits
```
wget https://download.anydesk.com/linux/anydesk_6.0.1-1_i386.deb -O anydesk.deb
```

- System is 64 bits
```
wget https://download.anydesk.com/linux/anydesk_6.1.1-1_amd64.deb -O anydesk.deb
```

Step 4. Install it
```
sudo dpkg -i anydesk.deb
```
You'll be asked to enter your sudo password.

```
sudo apt-get install -f
```
You'll be asked to press `Y`. Press `Y` as many times as asked.

Step 5. Run the software
Go to the terminal and type
```
anydesk
``` 

or go to the Menu and open `AnyDesk`

Step 6. Be happy

![Untitled design.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1642088491962/i52nHG7IS.png)

### Conclusion
In this article,  it was possible to learn how to install Anydesk on Ubuntu.

That's all for today.