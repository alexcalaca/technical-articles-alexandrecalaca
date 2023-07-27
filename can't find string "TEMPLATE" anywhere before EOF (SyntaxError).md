---
title: "can't find string "TEMPLATE" anywhere before EOF (SyntaxError)"
datePublished: Sat Jul 08 2023 05:07:18 GMT+0000 (Coordinated Universal Time)
cuid: cljtjnhu1000t09jrg4fhekp3
slug: cant-find-string-template-anywhere-before-eof-syntaxerror
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688792625490/19ad9847-7ca1-4874-9c5a-71ec7969e581.png
tags: programming-blogs, ruby

---

---

## Error

```apache
can't find string "TEMPLATE" anywhere before EOF (SyntaxError)
```

---

## Context

In a Ruby application, the error occurs when there is a syntax issue with the heredoc usage in the code, regardless of whether it is in a server or any other Ruby application.

---

## Situation

```apache
def self.create(attrs)        
        hash = {}
        hash["submitter"] = attrs["submitter"] || ""
        hash["quote"] = attrs["quote"] || ""
        hash["attribution"] = attrs["attribution"] || ""

        files = Dir["db/quotes/*.json"]
        names = files.map { |f| File.split(f)[-1]}
        highest = names.map { |b| b.to_i }.max
        id = highest + 1

        File.open("db/quotes/#{id}.json", "w") do |f|
          f.write <<TEMPLATE
        {
          "submitter": "#{hash["submitter"]}",
          "quote": "#{hash["quote"]}",
          "attribution": "#{hash["attribution"]}"
        }
        TEMPLATE
        end
        FileModel.new "db/quotes/#{id}.json"          
      end     
```

---

## Solution

The solution is to place the multiline string at the beginning of the code, ensuring that there are no spaces between the closing `}` bracket and the closing `TEMPLATE` identifier."

```ruby
     def self.create(attrs)        
        hash = {}
        hash["submitter"] = attrs["submitter"] || ""
        hash["quote"] = attrs["quote"] || ""
        hash["attribution"] = attrs["attribution"] || ""

        files = Dir["db/quotes/*.json"]
        names = files.map { |f| File.split(f)[-1]}
        highest = names.map { |b| b.to_i }.max
        id = highest + 1

        File.open("db/quotes/#{id}.json", "w") do |f|
          f.write <<TEMPLATE
{
  "submitter": "#{hash["submitter"]}",
  "quote": "#{hash["quote"]}",
  "attribution": "#{hash["attribution"]}"
}
TEMPLATE
        end
        FileModel.new "db/quotes/#{id}.json"          
      end      
```

---

## Explanation

The issue in the code was related to the incorrect usage of the heredoc syntax. In Ruby, heredoc is a way to define a multiline string literal using a special syntax with `<<`.

In this case, the `<<TEMPLATE` syntax is used to start a heredoc block with the identifier `TEMPLATE`, and it allows you to define a multiline JSON string.

The error occurred because the closing `TEMPLATE` identifier was not properly aligned or formatted. The closing identifier should be the only content on its line, without any leading or trailing whitespace or other characters.

By aligning the closing `TEMPLATE` identifier as the only content on its line, the Ruby interpreter can correctly identify the end of the heredoc block and treat the multiline string as intended.

With this correction, the `TEMPLATE` identifier is placed as the only content on the line immediately after the closing `}` bracket, without any leading or trailing whitespace. This ensures that the Ruby interpreter can correctly parse the multiline string and eliminate the syntax error.

---

## **Celebrate**

Way to go!

![The Office GIF - The Office Happy - Discover & Share GIFs](https://media.tenor.com/5F2BovYyscYAAAAd/the-office.gif align="left")

---

## **Let's become business friends**

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
