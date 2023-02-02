# Rails: How to setup rspec on Rails

1. #### Add `rspec` to the Gemfile;
    
    ```ruby
    group :development, :test do
      gem 'rspec-rails'
    end
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675273932198/a3ebfefb-d751-4c7f-ba1f-4b7f11da9a7c.png align="center")
    
2. #### Install the dependencies
    
    ```ruby
    bundle install
    ```
    
3. #### Check if it was installed correctly
    
    ```ruby
    gem list rspec
    ```
    
    You should see something like this
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675270137518/ca3d4399-74b5-4c3e-8894-3398cf5143bd.png align="center")
    
4. #### Check version
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675270504093/f3eff5da-7de7-4146-becd-375b51433012.png align="center")
    
5. #### Install rspec
    
    ```ruby
    rails generate rspec:install
    ```
    

You should see something like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272754256/bd847f6b-6609-488e-86ed-efd16f7b51e7.png align="center")

1. #### Generate a rspec model
    
    ```ruby
    rails generate rspec:model Product
    ```
    
    `Product` is a model. This is just an example.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675273534967/47892020-2583-416b-8ae0-640fdffb844e.png align="center")
    
2. #### Destroy a rspec model (Just in case you need it)
    
    ```ruby
    rails destroy rspec:model Product
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675273575198/5626d64d-2b40-471e-aa3c-98ef5a3a3685.png align="center")
    
3. #### Run a specific test on a single file
    
    ```ruby
    rspec spec/models/product_spec.rb:3
    ```
    
    In this example, the test starts in line 3.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675274971834/9f4b62f0-c527-4d15-84bf-61b0df8f3818.png align="center")
    
    You should see something like this
    
4. #### Run the tests for a single file
    
    ```ruby
    rspec spec/models/product_spec.rb
    ```
    
    You should see something like this
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675273752397/c965d80a-951d-4a3f-adf6-865d5ada1f29.png align="center")
    
5. #### Run all tests
    
    ```ruby
    rspec spec
    ```
    
    You should see something like this
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675274116757/9bd1e071-af05-452f-9f96-ef0ef8d68ad2.png align="center")
    
6. #### Celebrate! It's working.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif align="center")
    

---

#### Conclusion

In this article, we learned **how to setup Rspec on Rails**.

Let me know if you need any additional help.