---
external: false
title: 'What is HTML? 🤔'
description: ''
date: 2021-03-14
---

If you're interested in becoming a web developer -and did some research- you must have encountered the term HTML on many occasions, in the context of the front-end part of web development along with CSS and Javascript. We'll be covering today what HTML is as well as some foundational concepts about it.

## What is HTML?

HTML stands for Hypertext Markup Language.

**Hypertext** is text that is displayed on electronic devices that contains links (references) to other hypertext documents for readers to access easily.

**Markup Language** is a tool (technology) for structuring and representing data (text) and defining how it gets displayed. There are many markup languages such as XML, XHTML, HTML, MD...

Markup files are saved as plain text documents which are rendered by some type of reader. The HTML files we write gets rendered by the browser

What all markup languages have in common is how they distinguish between the content (text or data to be displayed) and the rules (how it gets displayed).

They use angle brackets ("<" and ">") to separate between the two.

For example:

```html
<p>Some data contained inside of an HTML paragraph element wouhou!</p>
```

Which brings us to the next point.

## Breaking down an HTML element

An HTML file comprises HTML elements, they are the building blocks of the document.

An HTML tag is a part of an HTML element, let's take an example:

```html
<p>Sick content here</p>
```

This is an HTML element that renders to a paragraph in a web browser with the content "Sick content here".

"< p >" and "< /p >" are (without the spaces) HTML tags, the first being an opening tag and the second a closing one.

We've got also HTML element attributes which are additional information about an HTML element, giving details about how it should be displayed.

So basically, the structure of an HTML element is as follows:

```xml
<nameOfTag nameOfAttribute=valueOfAttribute>Some content</nameOfTag>
```

You will also find that some HTML tags are self closing (do not require a closing tag) like **img, input, link, meta...**

**Note:** HTML tags are not case sensitive, meaning that "tagname", "tAgNaMe" and "TAGNAME" are all the same, although the [W3C](https://www.w3.org/) (an international community that develops standards for the Web) recommends using lowercase in HTML tag names.

## Example of an HTML file

This is a simple HTML file that contains the elements (which I will explain in a future article): html, head, title, body, heading (h1), and paragraph (p).

```html
<html>
  <head>
    <title>Title of Page</title>
  </head>
  <body>
    <h1>Main Heading</h1>
    <p>Insert some fancy text here boi</p>
  </body>
</html>
```

Which gets rendered by the browser to:

![Screenshot from 2021-03-14 21-09-07.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1615752642931/fv3Gp-J8K.png)

Quite unimpressive isn't it. Our web development (front-end wise) starts from this point, things will only get more interesting!

You notice that the page is, well, lacking in style, it's pretty dull. You're right it sure is.

> Because HTML is not responsible for styling the page and making it look good, its role is to structure the content of the page semantically.

**Returning to our previous example, ** we are assigning "Title of Page" as the page's title, "Main Heading" as a level 1 heading title and "Insert some fancy text here boi" as a paragraph. That's all what the HTML file is doing, structuring the content of the page in a meaningful way.

In order to get our page's style out of the 90's (aka more appealing and modern) we use a complementary technology called CSS (Cascading Style Sheets), we will cover it in the next article, so stay tuned!

## Thank you for reading!

That was a brief introduction to what HTML is, I hope you enjoyed the article!

Any feedback or constructive critique is warmly welcomed and appreciated, so please tell me what you think in the comments so I can better the quality. Thanks for reading ❤️!

Follow my blog and my [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one!
