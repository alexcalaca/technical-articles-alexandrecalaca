---
title: "Don't Let Slow Specs Slow You Down: How to Identify them"
datePublished: Mon Apr 24 2023 15:23:14 GMT+0000 (Coordinated Universal Time)
cuid: clguzmp3o000309mmemm0g85y
slug: dont-let-slow-specs-slow-you-down-how-to-identify-them
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682349690438/7e231abf-2cd0-4f9f-bcfe-dc4fa3f40e63.png
tags: programming-blogs, ruby, performance, ruby-on-rails, testing

---

### Greeting

Hey guys, how've you been? It's AC Alexandre Calaça here. Hope you enjoy this new article.

---

### Introduction

This article `Don't Let Slow Specs Slow You Down: How to Identify them` is the first part of a series dedicated to talk about rspec tests. The next article is going to be `Don't Let Slow Specs Slow You Down: How to Identify and Optimize Your RSpec Tests`.

---

#### Testing

The number of software programs is likely to continue growing rapidly, as new technologies and applications are developed and as more businesses and individuals rely on digital tools for their work and personal lives.

If there are more software and even more devices than people, we easily understand that one person interact with much more than 1 device and 2 software.

Considering that, softwares are an essential activity and affect people's lives.

The main idea about testing is to ensure that softwares behave the way they are supposed to and contribute to a better world.

Testing can help to improve the overall quality of the software by identifying areas for improvement and ensuring that the software meets the required standards and specifications.

In summary, testing is an essential part of software development as it helps to ensure that the software is of high quality, reliable, and meets the needs of users. By investing in testing, software developers can improve the overall performance and usability of the software, ultimately leading to a better user experience and increased user satisfaction.

---

### Rspec

#### About

RSpec is a testing framework for the Ruby programming language, designed to help developers write automated tests for their code. It provides a domain-specific language (DSL) for describing the behavior of Ruby code, allowing developers to write tests that are readable, expressive, and maintainable.

#### History

RSpec began life in 2005 as an experiment by Steven Baker, with early contributions from Dave Astels and Aslak Hellesøy. David Chelimsky joined the team that summer, and accepted leadership of the project in 2006.

RSpec 1.0 was released in May of 2007 and included many of the features that are still present in RSpec today.

In early 2010, after the release of RSpec 1.3, David and Chad began working on RSpec 2. RSpec 2 was released in October 2010 after nearly a year of effort.

Work on RSpec 3 began in July 2013 and it was released in June 2014.

In March 2020 RSpec Rails 4.0 was released, this release de-coupled it from the release cycles of the other RSpec gems in favor of remaining in step with Rails.

#### Authors

It all started as an experiment by Steven Baker in 2005, with early contributions from Dave Astels and Aslak Hellesøy.

Nowadays, the Rspec team members are Jon Rowe, Benoit Tigeot, Phil Pirozhkov, Xavier Shay and Yuji Nakayama

---

### How to Identify

Slow specs in RSpec are specs that take longer than the average time to run. They can slow down your test suite and make it harder to get quick feedback on your code changes.

In this article, we're going to identify them by using the `--profile`option provided by Rspec itself.

#### Option 1: `--profile`

Basically, in order to identify these slow specs, we're going to use `--profile` or `-p` provided by Rspec itself.

The full command would be one of the following:

```apache
rspec --profile
```

of

```apache
rspec -p
```

#### Option 2: `Gem` `gemrspec-benchmark`

`RSpec::Benchmark` is a an amazing performance testing matchers for RSpec to set expectations on speed, resources usage and scalability.

Integration and unit tests ensure that changing code maintains expected functionality. What is not guaranteed is the code changes impact on library performance.

Basically, in order to use `rspec-benchmark`, you need to include it in your Gemfile and run `bundle install`. Once it's installed, you can use the `:benchmark` tag in your RSpec examples and measure their run time.

As an example, the `perform_under` matcher answers the question of how long does it take to perform a given block of code on average. The measurements are taken executing the block of code in a child process for accurate CPU times.

```apache
expect { ... }.to perform_under(10).ms
```

This article is not going to focus on `gemrspec-benchmark.`

---

### The **\--profile** approach

#### Basic Usage

The `rspec --profile` command is used to run an RSpec test suite with profiling enabled, which provides a report of the slowest examples (tests) and groups (test suites) in the test suite. The profiling information is sorted by the execution time, with the slowest examples and groups listed at the top.

By default, it will automatically record the execution time of each example and group in your test suite, and then output a report of the 10 slowest examples and groups, along with their execution times.

#### Syntax

The basic usage is by running the following command in the terminal:

```apache
rspec --profile
```

#### With a file

`The rspec --profile` command is able to be used with a specific file or directory by specifying the file or directory path as an argument to the `rspec` command.

As an example, in case you want to run the `--profile` option on a specific file, you can run:

```apache
rspec --profile spec/path/to/your_spec.rb
```

The previous command will show the 10 slowest examples of the your\_spec.rb file.

#### With a directory

Similarly, if you want to run the `--profile` option on a specific directory, you can run:

```apache
rspec --profile spec/path/to/your_directory/
```

This will run all the tests in the `your_directory` directory and provide a report of the slowest tests, sorted by execution time.

Note that when running `--profile` on a specific file or directory, RSpec will only show the slowest tests within that file or directory.

#### Customize the number of examples

If no parameters are provided, the default number of examples is 10. It's possible to customize this number according to your needs.

You can customize the number of examples shown in the profiling report by using the `--profile` option along with the `n` flag, followed by the number of examples you want to see.

It would be like this:

```apache
rspec --profile 5
```

As an example, instead of 10 examples, if you want to get the top 15 slowest examples of one specific file, you can run:

```apache
rspec --profile --profile-examples 20 path/to/spec/file_spec.rb
```

The previous command will run the RSpec test suite and output a report of the 20 slowest examples in the `file_spec.rb` file, along with their execution times.

In case of a directory, the following command get the 20 slowest examples in all the files in the `directory`.

```apache
rspec --profile --profile-examples 20 path/to/spec/directory
```

#### Customize sorting

By default, RSpec sorts the profiling results by execution time, with the slowest examples and groups listed at the top. However, you can use the `--sort` option to change the sorting method

##### By impact

Impact is a combination of the number of times an example is run and the average execution time.

It would be like this:

```apache
rspec --profile --sort impact
```

The previous command is going to sort the examples and groups with the highest impact (i.e., the ones that are run the most frequently and/or take the longest to execute) will be listed at the top.

##### By alphabetical order

```apache
rspec --profile --sort name
```

The previous command will sort the profiling results alphabetically by example or group name.

---

### Calculate average time

To calculate the average time to run a spec in RSpec, you can use the `--profile` option with a specified number of examples. By default, RSpec will output the top 10 slowest examples. However, you can specify a different number of examples to output by using the `-p` or `--profile` option followed by the number of examples you want to see. The following command is configured to be 20 examples:

```apache
rspec --profile 20
```

Using this approach, you can sum the execution time of the first and the last example and get an average.

It's possible to sum the execution time of all elements and divide by the number of items.

It's also possible to get the element in the middle and consider it as the average.

There are many ideas and you need to choose the best for you.

In this article, we're not using the `gemrspec-benchmark` to accomplish this.

---

### Celebrate

If you read the article, kudos! you did a great job. You can definitely celebrate!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif align="center")

---

### Conclusion

That's all for today. Thanks for reading the article `Don't Let Slow Specs Slow You Down: How to Identify them.`

This article is the first part of a series dedicated to talk about rspec tests. The next article is going to be `Don't Let Slow Specs Slow You Down: How to Identify and Optimize Your RSpec Tests`.

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.