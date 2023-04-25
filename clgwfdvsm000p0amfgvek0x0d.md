---
title: "Don't Let Slow Specs Slow You Down: How to Identify them [Part II]"
datePublished: Tue Apr 25 2023 15:32:02 GMT+0000 (Coordinated Universal Time)
cuid: clgwfdvsm000p0amfgvek0x0d
slug: dont-let-slow-specs-slow-you-down-how-to-identify-them-part-ii
tags: programming-blogs, ruby, ruby-on-rails, testing, programming-tips

---

![Don't Let Slow Specs Slow You Down: How to Identify them](https://cdn.hashnode.com/res/hashnode/image/upload/v1682349690438/7e231abf-2cd0-4f9f-bcfe-dc4fa3f40e63.png?w=1600&h=840&fit=crop&crop=entropy&auto=compress,format&format=webp align="left")

### Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. Hope you enjoy this new article.

---

### Introduction

This article `Don't Let Slow Specs Slow You Down: How to Identify them [Part II]` is the second part of a series dedicated to talk about rspec tests. Just in case you didn't not check part I, just [click here.](https://blog.alexandrecalaca.com/dont-let-slow-specs-slow-you-down-how-to-identify-them-part-i)

The next article is going to be `Don't Let Slow Specs Slow You Down: How to Identify and Optimize Your RSpec Tests`.

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

or

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

### The `--profile` **approach**

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

If no parameters are provided, the default number of examples is 10. It's possible to modify this number according to your needs.

You can modify the number of examples shown in the profiling report by using the `--profile` option along with the `n` flag, followed by the number of examples you want to see.

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

---

### Customize sorting

By default, RSpec sorts the profiling results by execution time, with the slowest examples and groups listed at the top. However, you can use the `--sort` option to change the sorting method

#### By impact

Impact is a combination of the number of times an example is run and the average execution time.

It would be like this:

```apache
rspec --profile --sort impact
```

The previous command is going to sort the examples and groups with the highest impact (i.e., the ones that are run the most frequently and/or take the longest to execute) will be listed at the top.

#### By alphabetical order

```apache
rspec --profile --sort name
```

The previous command will sort the profiling results alphabetically by example or group name.

#### By the fastest

It sorts the profiling results by execution time in ascending order. So, it starts with the fastest examples and groups. This is the contrary of the Rspec's default sorting method, which is the slowest examples and groups listed at the top.

Take a look at a complete output example for the `fastest` sorting method:

```apache
Top 10 (fastest) examples:
  
  User
    creates a new user in the database (0.003 seconds)
    updates an existing user in the database (0.004 seconds)
    deletes a user from the database (0.005 seconds)
  
  Post
    creates a new article in the database (0.006 seconds)
    updates an existing article in the database (0.007 seconds)
    deletes an article from the database (0.008 seconds)
  
  Comment
    creates a new comment on an article (0.010 seconds)
    updates an existing comment on an article (0.011 seconds)
    deletes a comment from an article (0.012 seconds)
```

The previous output examples shows us the top 10 fastest examples, along with their execution times, grouped by the corresponding spec file and example description.

The `--sort fastest` option allows us to identify areas of our code that are performing well and may not require further optimization.

In case you want to be even more specific, you can customize the number of examples:

```apache
rspec --profile --sort fastest -n 30
```

#### By following the codebase's order

The `--sort defined` argument sorts the results by the order in which the examples are defined in the codebase, not by the Rspec's default, which is the execution time.

It's definitely an interesting way of visualizing your tests, since it follows the same order of the codebase.

This is an example of sorting the first 20 examples implemented in the codebase.

```apache
rspec --profile --sort defined -n 20
```

#### By ramdonly

This can help you identify potential issues that may not have been apparent when using other sorting methods.

In order to used, the `--sort random` argument must be used with the `--profile` option.

Take a look at an example:

```apache
rspec --profile --sort random
```

#### Complete list

It's possible to see a list of all the available sorting options for RSpec using the `--help` option. In this case, `grep` needs to be used.

Check it out:

```apache
rspec --help | grep sort
```

---

### Calculate average time

To calculate the average time to run a spec in RSpec, you can use the `--profile` option with a specified number of examples. By default, RSpec will output the top 10 slowest examples. However, you can specify a different number of examples to output by using the `-p` or `--profile` option followed by the number of examples you want to see. The following command is configured to be 20 examples:

**COPY**

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

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

### Summary

The [first article](https://blog.alexandrecalaca.com/dont-let-slow-specs-slow-you-down-how-to-identify-them-part-i) of the series focused on introducing the topic, the authors of rspec, and rspec itself. Besides, it showed several ways to identify slow rspec tests.

This article, which is the second part of the series, focused on how to customize sorting.

---

### Conclusion

That's all for today. Thanks for reading the article `Don't Let Slow Specs Slow You Down: How to Identify them [Part II].`

This article is the second part of a series dedicated to talk about rspec tests. Just in case you didn't not check part I, just [click here.](https://blog.alexandrecalaca.com/dont-let-slow-specs-slow-you-down-how-to-identify-them-part-i) The next article is going to be `Don't Let Slow Specs Slow You Down: How to Identify and Optimize Your RSpec Tests`.

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.