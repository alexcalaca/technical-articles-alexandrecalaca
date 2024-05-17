---
title: "How to implement a method with Action Job in Ruby on Rails"
datePublished: Mon Jun 19 2023 02:06:30 GMT+0000 (Coordinated Universal Time)
cuid: clj27tskb00010akx1whahkqo
slug: how-to-implement-a-method-with-action-job-in-ruby-on-rails
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/n0CTq0rroso/upload/a14925d48196d47400ccbcc31fd7cc1b.jpeg
tags: programming-blogs, ruby, web-development, ruby-on-rails

---

---

## Problem

How to implement a method with Action Job in Ruby on Rails

---

## Introduction

In Ruby on Rails, efficient background processing is crucial for handling time-consuming tasks without affecting the responsiveness of the application. Action Job, introduced in Rails 4.2, is a powerful feature that allows you to perform background processing seamlessly. It provides a clean and straightforward way to offload resource-intensive tasks to background workers, ensuring a smooth user experience.

By using Action Job, you can execute tasks asynchronously, improving the performance and scalability of your Rails application. This becomes especially useful when dealing with operations like sending emails, generating reports, processing large datasets, or interacting with external APIs, which would otherwise block the main thread and slow down the application.

---

## Situation

Let's consider a store called "AC Store".

A user chooses some products and adds them to the cart. In the end, when the user completes the checkout, they should receive an email.

In order to complete the checkout, the user needs to proceed with the payment. Let's create a method called `perform_payment` with Action Job.

---

### Steps

---

### Implement the method

The first step is to implement the method to be processed asynchronously.

In my example, my method is in the `order` class. This is a super simplified version of my class and my method, but this is not going to affect the understanding of the article.

You just need to understand that here is the implementation of the method that you want to use asynchronously.

```ruby
# app/models/order.rb
class Order < ApplicationRecord
  # There is code here

  def perform_payment(payment_type_params)
    # There is code here
    OrderMailer.received(self).deliver_later
  end
end
```

My original method contains logic related to performing the actual payment process.

After the payment process is performed, the line `OrderMailer.received(self).deliver_later` is invoked. This line triggers the sending of an email using the `OrderMailer` mailer class, specifically the received email template, which is passed the self object (the current order instance) as an argument.

The `deliver_later` method is called on the `OrderMailer.received(self)` expression. This method is provided by Active Job, It queues the email delivery as a background job to be processed asynchronously by the background job system.

The idea of the `deliver_later` method is to ensure that the email sending process does not block the current execution and is performed separately.

In summary, the `perform_payment` method in the Order model sends an email queued as a background job because of `deliver_later`, allowing it to be processed asynchronously.

---

### Create the job

```apache
rails generate job perform_payment
```

As you can see, two files were generated: a job test file and a job file.

By using the generator command, you don't have to manually create the job file and its associated code. It helps you save time and ensures consistency in the job class structure.

After running this command, you will find the `perform_payment_job.rb` file in the `app/jobs` directory, and it will contain a skeleton code structure for the job class.

The job file is used to define a specific job class, `PerformPaymentJob`, that will be responsible for performing payment-related tasks asynchronously.

You can then customize the `perform` method inside the generated file to implement the specific logic for performing payments asynchronously.

---

### Define the background job

Inside `app/jobs/perform_payment_job.rb`, insert the following code:

```apache
# app/jobs/perform_payment_job.rb
def perform(order, payment_type_params)
    order.perform_payment(payment_type_params)
end
```

The original perform\_payment method requires only one argument, which is `payment_type_params`.

The Active Job `perform` method requires two arguments: payment\_type\_params and order.

The `perform_payment` method is defined within the Order model or an associated class (`order.perform_payment`), it performs the necessary actions to perform a payment based on the provided payment parameters.

The complete code would be something like the following:

```ruby
# app/jobs/perform_payment_job.rb
class PerformPaymentJob < ApplicationJob
  queue_as :default

  def perform(order, payment_type_params)
      order.perform_payment(payment_type_params)
  end
end
```

---

### Queue the job

```apache
PerformPaymentJob.perform_later(@order, payment_type_params.to_h)
```

`PerformPaymentJob` refers to the job class named `PerformPaymentJob`. This job class is responsible for performing the necessary actions to charge an order.

`perform_later` is a method provided by Active Job, its idea is to enqueue the job for later execution by the background job system. The `perform_later` method ensures that the job is processed asynchronously, meaning it will be executed separately from the main request/response cycle.

The instance variable `@order` is the order object to be charged. It is passed as an argument to the `PerformPaymentJob`'s `perform` method when the job is executed.

The second parameter is `payment_type_params.to_h`. `payment_type_params` is a parameter that contains payment-related information submitted from a form or request.

By calling `.to_h` on `payment_type_params`, it converts the parameters into a hash. This hash is then passed as another argument to the `PerformPaymentJob`'s `perform` method when the job is executed. The specific implementation of how this hash is used in the `perform` method would be defined within the `PerformPaymentJob` class.

```ruby
# app/controllers/orders_controller.rb
def create
    @order = Order.new(order_params)
    @order.add_line_items_from_cart(@cart)

    respond_to do |format|
      if @order.save
        Cart.destroy(session[:cart_id])
        session[:cart_id] = nil

        PerformPaymentJob.perform_later(@order, payment_type_params.to_h)

        format.html { redirect_to store_index_url, notice: "Thank you for your order" }
        format.json { render :show, status: :created, location: @order }
      else
        format.html { render :new, status: :unprocessable_entity }
        format.json { render json: @order.errors, status: :unprocessable_entity }
      end
    end
  end
```

---

### Test it

YOu should see something like this in your terminal

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686281137193/609d0197-d039-46da-b408-952f55bf9c06.png align="center")

---

### **Be happy**

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's connect**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---