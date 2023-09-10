---
title: "How to install and configure the Faker gem to create data for a Ruby on Rails application"
datePublished: Sun Sep 10 2023 03:33:53 GMT+0000 (Coordinated Universal Time)
cuid: clmcwhvpf000409iefd867yhz
slug: how-to-install-and-configure-the-faker-gem-to-create-data-for-a-ruby-on-rails-application
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694315406567/af6584d2-dae5-4b83-99e7-b4a931b9912d.png
tags: tutorial, ruby, web-development, ruby-on-rails, testing

---

## Faker Gem

The Faker gem is a popular Ruby library used for generating fake or random data. It's particularly helpful in development and testing environments where you need placeholder data to simulate real-world scenarios without using actual sensitive or confidential information.

---

## Add the gem to the Gemfile

### Initial code

```plaintext
# Gemfile
gem 'faker'
```

### Complete code

```plaintext
source 'https://rubygems.org'
git_source(:github) { |repo| "https://github.com/#{repo}.git" }

ruby '2.7.4'

gem 'devise'
gem 'rails', '~> 6.1.7', '>= 6.1.7.4'
gem 'pg', '~> 1.1'
gem 'puma', '~> 5.0'
gem 'sass-rails', '>= 6'
gem 'webpacker', '~> 5.0'
gem 'turbolinks', '~> 5'
gem 'jbuilder', '~> 2.7'
gem 'simple_form'
gem 'faker'
gem 'bootsnap', '>= 1.4.4', require: false

group :development, :test do
  gem 'byebug', platforms: [:mri, :mingw, :x64_mingw]
end

group :development do
  gem 'web-console', '>= 4.1.0'
  gem 'rack-mini-profiler', '~> 2.0'
  gem 'listen', '~> 3.3'
  gem 'spring'
end

gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694315537075/ba424ca3-d667-490d-a2e4-3a24111001c5.png align="center")

---

## Install the gem and its dependencies

### Command

In your terminal emulator:

```plaintext
bundle install
```

### Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694315666582/1b9c294d-7953-4eb2-bd0b-ec684dbb7546.png align="center")

### Check installation

In your terminal emulator:

```plaintext
bundle info faker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694315744662/9ce1b494-47cf-4b62-959b-a813e724a7da.png align="center")

---

## Meet the generators

### Through the website

1. Go to the [website](https://github.com/faker-ruby/faker);
    
2. Go to [Generators](https://github.com/faker-ruby/faker#generators), which is in Table of Contents;
    

### Check generators

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694315951418/fdb95d65-718f-48bb-b338-badf18d778dc.png align="center")

---

## Implement seeds file

```plaintext
# db/seeds.rb
30.times do
  Course.create!([{
    title: Faker::Educator.course_name,
    description: Faker::TvShows::GameOfThrones.quote,
    user_id: 1
  }])
end
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694316521652/83ccd87f-8752-4a01-b24a-5a43057cb1f4.png align="center")

---

## Run seeds file

In your terminal emulator:

```plaintext
rails db:seeds
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694316569267/2c6a9d4f-eff4-472d-9663-a074f49e6e84.png align="center")

---

## Test it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694316660217/7048f1f2-c549-43fd-9bd6-8f2b4be8cb15.png align="center")

---

## **Celebrate**

You've made it!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article has been helpful to you. Please feel free to reach out if you have any questions. Your thoughts, suggestions, and corrections are more than welcome.

By the way, don't hesitate to drop your suggestions for new blog articles.

I look forward to seeing you next time.

---