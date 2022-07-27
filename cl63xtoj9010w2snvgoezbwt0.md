## Rails: NameError (uninitialized constant UserSerializer) error message

### Introduction
The `fast_jsonapi` is a a lightning fast JSON:API serializer for Ruby Objects. Its github page can be accessed [here](https://github.com/Netflix/fast_jsonapi).

The project is no longer maintained, but you might end up using it in some applications.

### Issue
This is the usual error message:
```
NameError (uninitialized constant UserSerializer)```



![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658934038111/3pWPKmVSQ.png align="left")

### Tests
None of the following tests worked:
- Leave terminal and open it again;
- Open a new tab;
- Open the terminal on VS Code;
- Open the terminal on Linux console;
- `Reload!` Rails console;

### Solution
For me, it worked to stop [spring](https://github.com/rails/spring), which is a Rails application preloader.

1. Exit Rails console
```
exit
```
2. Stop the `spring` Rails application preloader
```
spring stop
```
By the way, you can see all the available spring commands by using `help`
``` 
spring help
```
3. Enter `Rails console` again
```
rails c
```
or
```
rails console
```
4. Run the test command
Here, I tried:
```
UserSerializer.new( User.first ).serializable_hash
``` 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658934957525/QlJVKl0VB.png align="left")
or just type
```
UserSerializer
```
It'll return the class itself

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658935035043/6Wc9O9IzQ.png align="left")

5. `spring` is still working<br/>
In case you're a `spring` freak (Just kidding lol), `spring` is fine. 

Leave the terminal
```
exit
``` 
and there you go, `spring` is fine
```
spring status
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658935074938/4fasGTHib.png align="left")

### Conclusion
That's all. Hope you guys liked it. Let me know if you need any help.