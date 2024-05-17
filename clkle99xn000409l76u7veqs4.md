---
title: "How to create Rspec tests for your LeetCode solutions in Ruby?"
datePublished: Thu Jul 27 2023 16:53:49 GMT+0000 (Coordinated Universal Time)
cuid: clkle99xn000409l76u7veqs4
slug: how-to-create-rspec-tests-for-your-leetcode-solutions-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690476173459/41017732-a3fe-40de-a134-cdf352d86644.png
tags: ruby, ruby-on-rails, testing, rspec

---

---

## Topic

**How to create Rspec tests for your LeetCode solution problem in Ruby?**

---

### Requirements

Make sure your LeetCode solution is correct before writing the RSpec tests. The tests will verify that your solution behaves as expected for the provided test cases. If the tests fail, you can debug and fix your LeetCode solution accordingly.

---

## Create the rspec file

In the terminal, run the following:

```apache
touch most_frequent_even_element_spec.rb
```

The `touch` command in Linux is used to create an empty file or update the timestamp of an existing file without changing its content.

The primary purpose of the `touch` command is to modify the access and modification times of a file.

If the file doesn't exist, `touch` creates a new empty file with the specified name.

---

## Require the solution problem file

```apache
#  spec/most_frequent_even_element_spec.rb
require_relative "../lib/most_frequent_even_element"
```

In Ruby, `require_relative` is a method used to load a file located relative to the current file.

It allows you to include code from another Ruby file in your current file so that you can access classes, modules, methods, and constants defined in that external file.

By using `require_relative` in RSpec test files, you can easily include the implementation files that you want to test. This way, RSpec can access the classes and methods defined in the implementation files and test their functionality.

---

## Require rspec

```apache
require 'rspec'
```

So far, this is what we have

```apache
#  spec/most_frequent_even_element_spec.rb
require_relative "../lib/most_frequent_even_element"
require 'rspec'
```

---

### Test it

In the terminal, inside the project directory, run the following command:

```apache
rspec spec/most_frequent_even_element_spec.rb
```

Since you do not have any specific rspec tests so far, you should be able to see something like the following:

```apache
No examples found.


Finished in 0.00085 seconds (files took 0.04266 seconds to load)
0 examples, 0 failures
```

---

## Write a describe block

Write a describe block to define the behavior you want to test.

```apache
#  spec/most_frequent_even_element_spec.rb
RSpec.describe 'most_frequent_even_element' do
end
```

The complete code so far

```apache
#  spec/most_frequent_even_element_spec.rb
require_relative "../lib/most_frequent_even_element"
require 'rspec'

RSpec.describe 'most_frequent_even_element' do
end
```

In RSpec, `describe` is a fundamental block used for organizing and defining test examples. It is used to group related examples together and to describe the behavior of the code being tested.

The primary purpose of `describe` is to provide a clear and descriptive context for the tests, making them more readable and maintainable.

This is a basic syntax of `describe`:

```apache
describe "Topic I want to test" do
  # Test examples go here
end
```

The argument passed to `describe` is typically a string that describes the subject or feature being tested. It can be a class, a module, a method, or any other logical grouping of functionality.

---

Pay attention to the first word `RSpec`, because it is case-sensitive. So, as an example, if you type `rspec` instead of `RSpec`. you'll get the following error message:

```apache
Failure/Error:
  Rspec.describe 'most_frequent_even_element' do
  end

NameError:
  uninitialized constant Rspec
  Did you mean?  RSpec
```

---

### Test it

In the terminal, inside the project directory, run the following command:

```apache
rspec spec/most_frequent_even_element_spec.rb
```

Since you do not have any specific rspec tests so far, you should be able to see something like the following:

```apache
No examples found.


Finished in 0.00029 seconds (files took 0.06973 seconds to load)
0 examples, 0 failures
```

---

## Create a subject

```apache
#  spec/most_frequent_even_element_spec.rb
  subject { most_frequent_even(nums) }
```

The complete code would look like this

```apache
#  spec/most_frequent_even_element_spec.rb
require_relative "../lib/most_frequent_even_element"
require 'rspec'

RSpec.describe 'most_frequent_even_element' do
  subject { most_frequent_even(nums) }
end
```

In RSpec, `subject` is a helper method that is commonly used to define the object or instance that is the subject of the test.

It simplifies the test code and makes it more readable by allowing you to refer to the subject without repeating its instantiation or method calls in each example (spec).

The `subject` method can be used in two ways: implicit and explicit.

---

### Test it

In the terminal, inside the project directory, run the following command:

```apache
rspec spec/most_frequent_even_element_spec.rb
```

Since you do not have any specific rspec tests so far, you should be able to see something like the following:

```apache
No examples found.


Finished in 0.00025 seconds (files took 0.05076 seconds to load)
0 examples, 0 failures
```

---

## Create contexts

This can help you organize your tests and provide more meaningful descriptions for different scenarios.

For example, you can group tests based on different examples, input cases, edge cases, or specific conditions you want to test.

Some words are usually associated with contexts, such as **when, with, without** and **given**.

Since I'm creating rspec tests for the \[[**LeetCode Most Frequent Even Element**](https://leetcode.com/problems/most-frequent-even-element/)**\](**[https://leetcode.com/problems/most-frequent-even-element/](https://leetcode.com/problems/most-frequent-even-element/)), I decided to use the examples in contexts.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690079634239/bc7522fa-6bb9-448a-b450-7181c0b0f4e7.png align="center")

Take a look at the complete code so far:

```apache
# spec/most_frequent_even_element_spec.rb
require_relative "../lib/most_frequent_even_element"
require 'rspec'

RSpec.describe 'most_frequent_even_element' do
  subject { most_frequent_even(nums) }  

  context 'when the input array is empty' do
  end  

  context 'when the input array has no even elements' do
  end

  context 'when the input array contains even elements' do
    context 'when there is only one even element' do
    end

    context 'when there are over two even elements' do
    end

    context 'when there is a tie' do
    end    
  end
end
```

---

### Test it

In the terminal, inside the project directory, run the following command:

```apache
rspec spec/most_frequent_even_element_spec.rb
```

`most_frequent_even_element_spec.rb` is the filename. Since you do not have any specific rspec tests so far, you should be able to see something like the following:

```apache
No examples found.


Finished in 0.00016 seconds (files took 0.05174 seconds to load)
0 examples, 0 failures
```

---

## Create the first failing test

```apache
# spec/most_frequent_even_element_spec.rb
context 'when the input array is empty' do
    let(:nums) {[]}

    it 'returns the number -1' do
      is_expected.to eq(-9)
    end
  end
```

Just to make sure the test is really working, I want to make it fail. In the terminal, press the following command:

```apache
rspec spec/most_frequent_even_element_spec.rb:7
```

Now, it's expected to see an error message:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690081294238/6c2f05d1-62eb-46dd-b388-09e45a7af933.png align="center")

```apache
Failures:

  1) most_frequent_even_element when the input array is empty returns the number -1
     Failure/Error: is_expected.to eq(-9)
     
       expected: -9
            got: -1
     
       (compared using ==)
     # ./spec/most_frequent_even_element_spec.rb:11:in `block (3 levels) in <top (required)>'

Finished in 0.01873 seconds (files took 0.05334 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/most_frequent_even_element_spec.rb:10 # most_frequent_even_element when the input array is empty returns the number -1
```

---

## Make the first test pass

```apache
# spec/most_frequent_even_element_spec.rb
 context 'when the input array is empty' do
    let(:nums) {[]}

    it 'returns the number -1' do
      is_expected.to eq(-1)
    end
  end
```

Now, you should be able to see a new happy message:

```apache
Run options: include {:locations=>{"./spec/most_frequent_even_element_spec.rb"=>[7]}}
.

Finished in 0.00078 seconds (files took 0.05265 seconds to load)
1 example, 0 failures
```

---

## Add the other tests

Just to show you as an example, this is my complete rspec file.

```apache
# spec/most_frequent_even_element_spec.rb
require_relative "../lib/most_frequent_even_element"
require 'rspec'

RSpec.describe 'most_frequent_even_element' do
  subject { most_frequent_even(nums) }  

  context 'when the input array is empty' do
    let(:nums) {[]}

    it 'returns the number -1' do
      is_expected.to eq(-1)
    end
  end

  context 'when the input array has no even elements' do
    let(:nums) {[1, 9, 3, 3, 7, 5, 5]}

    it 'returns -1' do
      expect(subject).to eq(-1)
    end
    
  end

  context 'when the input array contains even elements' do
    context 'when there is only one even element' do
      let(:nums) {[8, 9, 3, 3, 7, 5, 5]}

      it 'returns the only one even element' do
        expect(subject).to eq(8)
      end
    end

    context 'when there are over two even elements' do
      let(:nums) {[4, 2, 2, 3, 7, 4, 4]}

      it 'returns the most frequent' do
        expect(subject).to eq(4)
      end
    end

    context 'when there is a tie' do
      let(:nums) {[4, 2, 2, 3, 2, 4, 4]}

      it 'returns the smallest' do
        expect(subject).to eq(2)
      end
    end    
  end
end
```

---

## **Github Repository**

In case you want to follow along, **in progress.**

---

## **Celebrate**

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become friends**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---