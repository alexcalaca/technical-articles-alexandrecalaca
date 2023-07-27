---
title: "A step-by-step guide to setting up rspec in a pure Ruby project"
datePublished: Mon Jun 05 2023 15:11:19 GMT+0000 (Coordinated Universal Time)
cuid: cliizp5sn000509l8c1v90giz
slug: a-step-by-step-guide-to-setting-up-rspec-in-a-pure-ruby-project
tags: programming-blogs, ruby, 2articles1week

---

## Problem

A step-by-step guide to setting up rspec in a pure Ruby project

---

## Situation

When it comes to testing Ruby applications, RSpec has emerged as a widely adopted testing framework, offering a powerful and expressive syntax.

While many tutorials focus on integrating RSpec with popular Ruby frameworks like Ruby on Rails, the process of using RSpec with pure Ruby often goes unnoticed.

In this comprehensive guide, we aim to bridge that gap by providing you with a step-by-step walkthrough on how to install and configure RSpec with pure Ruby.

---

## Solution

* Create project
    
* Configure Gemfile
    
* Configure rspec
    
* Create a spec
    
* Create a class
    

---

### Create project

#### Create the directory's project

```ruby
mkdir ruby-challenges
```

---

### Configure Gemfile

#### Create the Gemfile

In the root of the app, create the `Gemfile` by running the following command:

```ruby
bundle init
```

The output should be something like this

```ruby
Writing new Gemfile to /home/alexandre/var/www/ruby-challenges/Gemfile
```

---

#### Update Gemfile

Insert the following code into the `Gemfile`:

```ruby
# ruby-challenges/Gemfile

source "https://rubygems.org"

gem "rspec"
```

---

#### Install

This step is focused on installing rspec based on the content of the `Gemfile`.

```ruby
bundle install --path .bundle
```

Your output should look like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685714103954/e322be97-0352-4434-8645-122ea55c9503.png align="center")

---

### Configure rspec

#### Create spec's directory

inside the project's directory `ruby-challenges`

```ruby
mkdir spec
```

At the moment, this should be your project's structure: Run `ls`

```ruby
ls
```

the output should look something like this

```ruby
Gemfile  spec
```

---

### Create a spec

#### Create a spec file

```ruby
# ruby-challenges/spec
touch string_checker_spec.rb
```

---

#### Initiate the spec implementation

```ruby
# ruby-challenges/spec/string_checker_spec.rb

describe StringChecker do

end
```

---

#### Test

Let's test what we already have so far. In the root of the app:

```ruby
# ruby-challenges/
bundle exec rspec
```

Your output would look something like the following picture

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685716712080/19c98b65-6a51-48ce-bbff-0874dbed83e4.png align="center")

In this case, this error is totally normal and it indicates we don't have a `StringChecker` class.

---

#### Require the model

This step consists in inserting the model file name into the rspec file.

```apache
# ruby-challenges/spec/string_checker_spec.rb
require "string_checker"

describe StringChecker do

end
```

> My model name needs to be called string\_checker.rb

---

### Create a class

#### Create a lib directory

Insite the root of the application

```apache
mkdir lib
```

So far, this is the directory's structure:

```apache
Gemfile  Gemfile.lock  lib  spec
```

---

#### Create the class

```apache
touch string_checker.rb
```

---

#### Implement the class

```ruby
# ruby-challenges/lib/string_checker.rb:1
class StringChecker
  
end
```

---

### Test it

```apache
bundle exec rspec
```

Your output should look something like this

```apache
No examples found.


Finished in 0.00007 seconds
0 examples, 0 failures
```

---

## Repository

Check it out [here](https://github.com/alexcalaca/rspec-with-ruby).

---

### Celebrate

There are no errors. Time to celebrate.

![Best Michael Scott Reaction GIFs | Gfycat](https://thumbs.gfycat.com/FriendlyRadiantBumblebee-max-1mb.gif align="left")

---

## **Let's get to know each other**

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
