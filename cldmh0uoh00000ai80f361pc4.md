# Rspec: Could not find generator 'rspec:install'. Maybe you meant 'assets', 'channel' or 'scaffold'

### Introduction

`rspec-rails` brings the RSpec testing framework to Ruby on Rails as a drop-in alternative to its default testing framework, Minitest.

Rspec looks a lot like plain English.

---

### What's the error message?

```ruby
Could not find generator 'rspec:install'. Maybe you meant 'assets', 'channel' or 'scaffold'
```

The error message says that it was not possible to find the above generator.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675271336843/481f48e2-5118-47a0-a2e8-07628f32fdc3.png align="center")

---

### When does it happen?

It happens when you try to run `rails generate rspec:install`

```ruby
rails generate rspec:install
```

---

### How to solve the error?

Make sure that:

1. #### The command is spelled correctly
    
    `rails generate rspec:install`
    
2. #### Rspec gem is inside :development and :test blocks (Gemfile)
      
    `gem 'rspec-rails'`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675273949902/fd496465-734b-4988-91dd-577acf06449f.png align="center")
    
4. #### Rspec is installed
    
    `gem list rspec`
    
5. #### Stop spring
    
    `bin/spring stop`
    
    This one worked for me.
    
6. #### Try again
    
    `rails generate rspec:install`
    
    You should see something like this
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272754256/bd847f6b-6609-488e-86ed-efd16f7b51e7.png align="center")
    
7. #### Celebrate
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif align="center")

---

### Conclusion

In this article, we learned `how to setup rspec on Ruby on Rails.`

Let me know if you need any additional help.