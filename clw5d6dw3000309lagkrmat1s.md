---
title: "How to configure FactoryBot with Rspec in a Rails 7 application"
datePublished: Mon May 13 2024 19:35:44 GMT+0000 (Coordinated Universal Time)
cuid: clw5d6dw3000309lagkrmat1s
slug: how-to-configure-factorybot-with-rspec-in-a-rails-7-application
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/UzHQOxVxqgw/upload/9b2f807de43160a402e4e47186105bb8.jpeg
tags: ruby, ruby-on-rails, alexandrecalaca

---

## FactoryBot Rails

FactoryBot is a Ruby library for setting up Ruby objects as test data in a test suite. Specifically, FactoryBot Rails is an extension of FactoryBot designed to work seamlessly with Ruby on Rails applications.

In the context of testing Rails applications, FactoryBot Rails provides a convenient way to define and create factories for ActiveRecord models.

Factories are used to generate instances of model objects with predefined attributes, making it easier to set up test data for various scenarios.

---

### Add to the Gemfile

According to the [documentation](https://github.com/thoughtbot/factory_bot_rails), add `factory_bot_rails` to your Gemfile in both the test and development groups:

```javascript
group :development, :test do
  gem 'rspec-rails'
  gem 'factory_bot_rails'
  gem "debug", platforms: %i[ mri mingw x64_mingw ]
end
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707709287729/03067879-6309-430b-b243-0bc70bf6ba12.png align="center")

---

### Install the dependencies

```javascript
bundle install
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707709367592/a56d818f-eb7d-45e6-85d0-63433360aa39.png align="center")

---

## Configure FactoryBot Rails

The next parts is to configure `FactoryBotRails`.

---

### Create a folder

```javascript
 mkdir spec/support
```

---

### Create the configuration file

```javascript
touch spec/support/factory_bot.rb
```

---

### Add the configuration

```javascript
# spec/support/factory_bot.rb
RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods
end
```

This configures RSpec to include FactoryBot methods (like `create`, `build`, etc.) in your tests and ensures that FactoryBot factories are loaded before the test suite runs.

---

## Let's test

---

### Create a rspec test file

```javascript
 rails generate rspec:model Author
```

---

### Use the `create` method

We don't have any factories yet, but let's try to use the `create` method anyway.

```javascript
# spec/models/author_spec.rb
require 'rails_helper'

RSpec.describe Author, type: :model do  
  it 'creates a valid author object using FactoryBot' do    
    author = FactoryBot.create(:author)
    
    expect(author).to be_valid
    expect(author.persisted?).to eq(true)
  end
end
```

---

### Run the tests

```javascript
bundle exec rspec spec/models/author_spec.rb -fd
```

output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707710347349/e0237557-f9e6-4405-ad0f-85e7d5d64ed2.png align="center")

Great, it tried to create an object using FactoryBot.

---

### Use the `build` method

```javascript
# spec/models/author_spec.rb
RSpec.describe Author, type: :model do  
    it 'builds a valid author object using FactoryBot' do    
        author = FactoryBot.build(:author, name: 'John Doe')
        
        expect(author).to be_valid
        
        author.save
        
        expect(author.persisted?).to eq(true)
    end
end
```

Output of the complete code

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707710510752/e908203b-ad53-4d61-a98d-cc977d9e7934.png align="center")

---

### Run the tests

```javascript
bundle exec rspec spec/models/author_spec.rb -fd
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707710654312/2a597e13-c96d-4b19-a3a5-c960ad305278.png align="center")

---

## Create a factory

---

### Create the `factories` folder

```javascript
mkdir spec/factories
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707710831797/f2da157f-a738-4b64-b592-c6846f02caf7.png align="center")

---

### Create the file

```javascript
touch spec/factories/authors.rb
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707710886043/f8b32a3a-9568-48c9-90e4-9fe7ce22583d.png align="center")

---

### Add the factory

```javascript
# spec/factories/authors.rb
FactoryBot.define do
  factory :author do
    name { 'Toby Flanderson' }
  end
end
```

---

## Run the tests

The error messages so far have indicated that we don't have registered factories, but this time we do.

Let's run the tests; all the tests should fail.

---

### Run

```javascript
bundle exec rspec spec/models/author_spec.rb -fd
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707711162643/0ac31eaf-2c66-4eff-b8f2-8d0b35d1e5f8.png align="center")

---

## **Done**

---

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

## **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@devcenterguides)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

## **Final thoughts**

Thank you for reading this article.

If you have any questions, thoughts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.