## Rails: uninitialized constant #<Class:0x00007f616c033c50>::FriendlyId
error message

### Greetings
Hey my favorite devs, how's it going?<br/>
Hope you're good.<p/>
Let's get down to business. Shall we?

### Introduction
`FriendlyId` is an amazing Ruby gem that is responsible for slugging and permalink plugins for Active Record. It lets you create pretty URLs and work with human-friendly strings as if they were numeric ids.

### Error
This is the usual error message:
```
uninitialized constant #<Class:0x00007f616c033c50>::FriendlyId```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1661452511978/UB8HfC1fB.png align="left")

Here, my environment configuration is with `Rails 6.1.6.1` and `friendly_id 5.2.4`.

### Solutions
#### 1. Check if you have a typo
Come back to the  `FriendlyId`'s [github page](https://github.com/norman/friendly_id) and follow the steps again, I mean, check your controller and model code.

#### 2. Restart the Rails server

On console, run
1. `CTRL + C` to stop the server (in case your server is running);
2. `rails s` to start the server again

For me, the solution was this.

### Conclusion
That's all. Hope you guys liked it. Let me know if you need any help.
