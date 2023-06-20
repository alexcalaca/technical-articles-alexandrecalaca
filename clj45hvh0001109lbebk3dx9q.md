---
title: "Understand the underscore method provided by ActiveSupport in Ruby on Rails"
datePublished: Tue Jun 20 2023 10:36:47 GMT+0000 (Coordinated Universal Time)
cuid: clj45hvh0001109lbebk3dx9q
slug: understand-the-underscore-method-provided-by-activesupport-in-ruby-on-rails
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687257361789/8a360e89-fab4-43da-823e-e57d290800ad.png
tags: programming-blogs, ruby, web-development, ruby-on-rails

---

---

## The underscore method

This method is used to convert a string from CamelCase, also called PascalCase, to underscored snake\_case.

The method is provided by ActiveSupport.

---

## ActiveSupport

The `ActiveSupport` module in Rails plays a fundamental role in enhancing the functionality and convenience of the framework. It serves as an extension to the Ruby standard library, providing a bunch of utility methods and enhancements that enrich the development experience.

---

### Naming conventions

Additionally, `ActiveSupport` actively contributes to the adherence of Rails' naming conventions by providing methods like `underscore`, which enables the seamless conversion of ConstantNames to file\_names and other cases.

---

## The underscore method usage

### Database Table Names

When defining database tables in Rails, the convention is to use pluralized, underscored names. For example, if you have a class named `UserGroup`, calling `underscore` on it would return 'user\_groups', which can be used as the corresponding database table name.

---

### File Naming

Rails follows a consistent file naming convention, where files are named using snake\_case and classes follow the camel case pattern.

For instance, if you have a model class named `ArticleCategory`, using `underscore` will convert it to 'article\_category.rb', which is the expected filename.

---

### URL Routes

`Route URLs` are typically defined in snake\_case format. When generating URLs or working with routing, using `underscore` helps ensure consistency with route naming.

For example, if you have a route for `ArticleCategoryController`, calling `underscore` on it will provide 'article\_category', which can be used in routing definitions.

---

## Implementation

```ruby
# File activesupport/lib/active_support/inflector/methods.rb, line 92
    def underscore(camel_cased_word)
      return camel_cased_word unless /[A-Z-]|::/.match?(camel_cased_word)
      word = camel_cased_word.to_s.gsub("::".freeze, "/".freeze)
      word.gsub!(inflections.acronyms_underscore_regex) { "#{$1 && '_'.freeze }#{$2.downcase}" }
      word.gsub!(/([A-Z\d]+)([A-Z][a-z])/, '\1_\2'.freeze)
      word.gsub!(/([a-z\d])([A-Z])/, '\1_\2'.freeze)
      word.tr!("-".freeze, "_".freeze)
      word.downcase!
      word
    end
```

### Scope resolution operator

The line `return camel_cased_word unless /[A-Z-]|::/.match?(camel_cased_word)` is going to check if the input contains any uppercase letters or the scope resolution operator ::.

If it doesn't, indicating that the word is already underscored or doesn't require conversion, the original word is returned as is.

If the word needs to be converted, the code proceeds with the conversion logic.

---

### Name namespaces

The line `word = camel_cased_word.to_s.gsub("::".freeze, "/".freeze)` replaces the :: scope resolution operator with a forward slash /.

This step is done to handle namespaced class/module names and convert them into a path-like format.

---

### Find acronyms

The next line `word.gsub!(inflections.acronyms_underscore_regex) { "#{$1 && '_'.freeze }#{$2.downcase}" }` handles special cases for acronyms.

It uses a regular expression defined in the inflections module to find acronyms within the word and replaces them with an underscore followed by the lowercase version of the acronym. This ensures consistent formatting of acronyms within the underscored word.

---

### Conversion

The two subsequent `gsub!` lines handle the conversion of CamelCase to snake\_case based on regular expressions.

---

### Handle hyphens

The line `word.tr!("-".freeze, "_".freeze)` replaces any hyphens (-) with underscores (\_) to handle cases where hyphens are used instead of spaces or underscores.

---

### Convert to lowercase

`word.downcase!` converts the entire word to lowercase, ensuring consistency in the output format.

---

### Return

The resulting `word`, which was created at the beginning of the mehtod, is then returned as the underscored version of the camel\_cased\_word (the input).

---

### **Be happy**

You got here. Way to go!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

### **Let's connect**

* [**Github**](https://github.com/alexcalaca)
    
* [**LinkedIn**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**Hashnode**](https://hashnode.com/onboard?next=/@alexandrecalaca)
    
* [**Youtube**](https://www.youtube.com/@alexandrecalacaofficial)
    

---

## **Final thoughts**

I hope this article helped you. Let me know if you have any questions. Your thoughts, suggestions and corrections are more than welcome. By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---