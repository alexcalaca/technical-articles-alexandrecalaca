---
title: "How to handle ActiveRecord::RecordNotFound exception in Rails?"
datePublished: Mon May 22 2023 02:22:38 GMT+0000 (Coordinated Universal Time)
cuid: clhy82pcb000409lc8gf4bfgc
slug: how-to-handle-active-record-record-not-found-exception-in-rails
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/XWar9MbNGUY/upload/4d971485193458121285eb2436811675.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails, 2articles1week

---

> TL; DR: The best strategy is the one based on your needs

---

## Problem

The `ActiveRecord::RecordNotFound` exception in Rails occurs when a specific record is not found in the database.

Rails usually render an error page.

---

## Error

Let's check the exception from different angles.

### Full message

```ruby
ActiveRecord::RecordNotFound in XXXController#action
```

### Snapshot

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684717709734/4553ad36-bcb7-42f0-bd6a-19de71372e33.png align="center")

---

### Explanation

It's important to note that this error typically occurs when trying to find a single record by its unique identifier or a specific set of conditions.

It typically happens when using methods bang methods to retrieve a record based on certain conditions, but the record matching those conditions does not exist.

It is different from a general database query returning an empty result set, as it specifically relates to a missing individual record.

---

## Solutions

### 1- Show the default error page

Rails way to handle it. In this case, you don't need to provide any additional configuration or code.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684717909911/c3a66a10-b46a-45b6-bc62-fb28d23fbb11.png align="center")

---

### 2-Use `begin` and `rescue`

```apache
class PostsController < ApplicationController
  def show
    begin
      @post = Post.find(params[:id])
    rescue ActiveRecord::RecordNotFound
      flash[:error] = "The requested post could not be found."
      redirect_to root_path
    end
  end
end
```

By using begin and rescue, you can control how your program handles exceptions, providing error handling and recovery mechanisms to ensure your code behaves as expected even when errors occur.

---

### 3- Rescue from method

```apache
class PostsController < ApplicationController
  rescue_from ActiveRecord::RecordNotFound, with: :handle_record_not_found

  def show
    @post = Post.find(params[:id])
  end

  private

  def handle_record_not_found
    flash[:error] = "The requested post could not be found."
    redirect_to root_path
  end
end
```

By using `rescue_from` you can centralize the handling of specific exceptions in one place within your controller. This approach allows you to keep your code clean and avoid repetitive error handling in multiple actions.

It will be invoked when the `ActiveRecord::RecordNotFound` exception occurs. Inside this method, you can customize the behavior for handling the exception.

---

## Best error handling strategy

The best approach depends on the specific needs of your application, the complexity of your error handling requirements, and the desired level of consistency in handling `ActiveRecord::RecordNotFound` errors.

You can choose either method or even a combination of both based on the context and structure of your Rails application.

Anyway, let's point out some details about both:

---

* ### begin and rescue
    

In general, if you have specific error handling logic that differs between different actions in a controller, using `begin` and `rescue` blocks within each action may be more appropriate.

---

* ### rescue from
    

On the other hand, if you want a consistent handling approach for `ActiveRecord::RecordNotFound` throughout a controller or across multiple controllers, using `rescue_from` provides a cleaner and more centralized solution.

---

## Conclusion

This error is an essential part of Rails' robust error handling system, providing a clear and informative message to users when a record is not found.

> The `ActiveRecord::RecordNotFound` helps maintain data integrity and ensures that users are aware of the situation and can take appropriate action.

it's important to note that Rails offers various techniques to handle this error, including `rescue_from` and `begin`/`rescue` blocks, allowing developers to tailor their error handling approach based on specific requirements and context.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684471277772/95b437a8-003b-4172-a9c6-5ebd918e3bb1.png align="center")

---

## Let's connect

* [Github](https://github.com/alexcalaca)
    
* [LinkedIn](https://linkedin.com/in/alexandrecalacaofficial)
    
* [Hashnode](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [Youtube](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## Final thoughts

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---
