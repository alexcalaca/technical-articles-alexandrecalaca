---
title: "Say Goodbye to Input Headaches: How to Format Brazilian Cellphone Numbers in JavaScript easily"
datePublished: Tue May 09 2023 15:04:13 GMT+0000 (Coordinated Universal Time)
cuid: clhgek0l0000109mkf2ctaw86
slug: say-goodbye-to-input-headaches-how-to-format-brazilian-cellphone-numbers-in-javascript-easily
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/B4ndBW2R_Q8/upload/acae2c1b7b9f4c47767e0f2f77417a66.jpeg
tags: programming-blogs, javascript, web-development, hashnode, 2articles1week

---

---

### Greeting

Hey guys, how've you been? It's AC, Alexandre Calaça here. Hope you enjoy this new article.

By the way, I would be glad to receive your feedback about it

---

### Objective

In this article, we will explore how to create a super simple input mask for Brazilian cellphone numbers using vanilla JavaScript.

---

### Introduction

An input mask is a useful feature for ensuring that data entered by users is in a specific format.

Input masks encourage users to provide accurate data, and can help to improve the user experience of filling out forms.

In order to accomplish this, we're going to use vanilla Javascript.

---

#### Vanilla Javascript

Vanilla JavaScript refers to the use of JavaScript without any additional libraries or frameworks. It is the purest form of JavaScript, using only the core language features and built-in browser APIs to perform tasks and manipulate the Document Object Model (DOM).

The term "vanilla" in this context is often used to contrast with the use of third-party libraries or frameworks that add additional functionality or abstractions to JavaScript. Examples of popular JavaScript libraries and frameworks include jQuery, React, Vue, Angular, and many others.

---

#### Input mask

An input mask is a feature in a form field that restricts the format of data that can be entered by a user. It provides a pattern or a template for the data entry that the user must follow. The input mask can help to ensure that the data entered is in the correct format and meets the required standards.

Input masks are often used in web forms or applications to ensure that the data entered by users is consistent and conforms to a particular format. For example, an input mask for a phone number field might require that the user enter the phone number in a specific format such as (123) 456-7890. The input mask will enforce this format and reject any input that does not match the pattern.

---

### Coding time

1. #### Html view page
    
    Create an html page
    

```ruby
<label for="phone">Phone:</label>
<input type="text" data-js="sinput" id="phone" />
```

The label is created using the tag with the text "Phone:" and the for attribute set to "phone". This is used to associate the label with the input field.

The input field is created using the tag with the following attributes:

* type="text": specifies that the input field should accept text input.
    
* data-js="input": a custom attribute that could be used by JavaScript to select this input field.
    
* id="phone": a unique identifier for the input field that is referenced by the for attribute of the label.
    

---

1. #### CSS
    

#### Create a stylesheet file

```ruby
body {
  padding: 30px
}

input {
  font-size: 20px
}
```

This is CSS code for styling a web page.

The first rule targets the entire body of the HTML document and sets a padding of 30 pixels, which creates space between the content and the edges of the browser window.

The second rule targets all input elements and sets their font size to 20 pixels. This will make the text inside the input boxes larger and easier to read.

---

1. #### Javascript
    
    He is the complete Javascript code.
    

```ruby
const $input = document.querySelector('[data-js="input"]')
$input.addEventListener('input', handleInput, false)

function handleInput (e) {
  e.target.value = phoneMask(e.target.value)
}

function phoneMask (phone) {
  return phone.replace(/\D/g, '')
    .replace(/^(\d)/, '($1')
    .replace(/^(\(\d{2})(\d)/, '$1) $2')
    .replace(/(\d{5})(\d{1,5})/, '$1-$2')
    .replace(/(-\d{4})\d+?$/, '$1');
}
```

This code creates a phone number input mask using regular expressions in JavaScript.

It defines a function called `phoneMask` that takes a phone number as a parameter and returns a formatted phone number.

---

1. #### Live view
    
    A live view can be accessed [here.](https://codepen.io/alexcalaca/pen/XWxzWKG)
    

This is just a screenshot of the page

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683631670634/416fa9bb-bb4a-47a8-9dc8-7f48e1c3d26a.png align="center")

---

![orange and white tabby cat](https://images.unsplash.com/photo-1606740256513-d13624dde670?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1000&q=80 align="left")

---

### Zooming in

Let's check the first two lines of code

```apache
# The first line selects the input element with a data attribute of "input". 
const $input = document.querySelector('[data-js="input"]')

# The second line adds an event listener to the input element, which calls the handleInput function whenever there is an input event on the input element.
$input.addEventListener('input', handleInput, false)
```

The Next line is a function call

```apache
# The handleInput function gets the value of the input element and passes it to the phoneMask function
function handleInput (e) {
  e.target.value = phoneMask(e.target.value)
}
```

The next part is the `phoneMask` function itself.

```apache
function phoneMask (phone) {
  return phone.replace(/\D/g, '')
    .replace(/^(\d)/, '($1')
    .replace(/^(\(\d{2})(\d)/, '$1) $2')
    .replace(/(\d{5})(\d{1,5})/, '$1-$2')
    .replace(/(-\d{4})\d+?$/, '$1');
}
```

* Remove all non-digit characters
    
    The `phoneMask` function removes all non-digit characters using the `/\D/g` regular expression, which matches all non-digit characters, and then applies a series of regular expression replacements to format the phone number.
    
* Add an opening parenthesis before the first digit
    
    The first `replace` adds an opening parenthesis before the first digit, if it's not already there.
    
* Add a closing parenthesis after the second digit  
    The second `replace` adds a closing parenthesis and a space after the second digit if there are a total of two digits at the start of the phone number.
    
* Add a hyphen after the fifth digit  
    The third `replace` adds a hyphen after the fifth digit.
    
* Remove any extra digits  
    The last `replace` removes any extra digits at the end of the phone number, leaving only the hyphen and the last four digits.
    

Finally, the `phoneMask` function returns the formatted phone number, which is then set as the value of the input element in the `handleInput` function, updating the input field with the formatted phone number.Return

---

## Summary

In this article, we learned an absolute easy way to create a input mask for Brazilian Cellphone Numbers.

---

## Celebrate

You got here. Great! Way to go! you did a great job.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1675272855269/884b16d0-43b7-41f0-9ac3-83ab90f4e9ca.gif?auto=format,compress&gif-q=60&format=webm align="left")

---

## Conclusion

That's all for today. Thanks for reading this article.

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.

---
