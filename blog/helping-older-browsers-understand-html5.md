---
title: 'Helping Older Browsers Understand HTML5'
description: 'In this blog article I explain how older verions of web browsers interpret unknown HTML5 elements, how to help them with that, and the recommended approach to that.'
canonicalUrl: "https://mohamedyamani.com/blog/helping-older-browsers-understand-html5/"
pubDate: 2021-08-06
image: "/images/thumbnails/helping-older-browsers-understand-html5.jpg"
imageAlt: "abandoned old black sedan with broken windows"
---

## Table of content

- Introduction
- Ancient browsers that do not support HTML5
- How do these browsers interpret HTML5 semantic elements?
- Okay, so what's the solution?

## Introduction

When HTML5 was released it brought semantic HTML elements to the table which in turn frequently replace the famous _divs_ and _spans_ that are notoriously used everywhere.

The use of these semantic elements is very important, some of the reasons behind that being:

- Offering people with disabilities a better navigation experience by creating a clear hierarchy of the content of the page for screen readers to parse.
- Helps your website's SEO ranking (Search Engine Optimization) by facilitating the indexing of the website by search engines.
- HTML elements now give a descriptive meaning to their content. An _aside_ is a lot more descriptive than the general-everywhere-use of _div_ or _span_.

## Ancient browsers that do not support HTML5

Unfortunately though, not all browsers support HTML5 features (fully and/or partially) and that complicates things.

We can't write our HTML twice; one that is semantic for browsers that are compatible and one for the older versions that are not. Because that is resource consuming in terms of authoring and maintenance.

And we obviously cannot neglect the ones that do use ancient browsers (yes, some people do, surprisingly) because that could potentially mean decrease in revenue and visibility since a portion of people won't be able access our website properly.

#### Now these cursed browsers are (partial to no compatibility for semantic HTML):

- Mozilla Firefox version 2 to 20
- Google Chrome version 4 to 25
- Safari version 3.1 to 6
- Internet Explorer version 6 to 9

## How do these browsers interpret HTML5 semantic elements?

That's a good question, it's an edge case that needs to be treated.

Naturally, incompatible browsers with HTML5 features won't recognize the new semantic elements like _nav_, _header_, _footer_ etc.

So how do they parse them?

Browsers treat them as _inline_ elements. Meaning they would go with the flow of text, they do not start a new line (the same default behavior of _img_ and _span_ for example).

## Okay, so what's the solution?

- ### The "meh" approach

Some of the older browser versions allow CSS rules to be associated with semantic elements (for example IE9 was the first of IE to adopt this), we will be using that to our advantage.

All you have to do is select the semantic elements and change their _display_ (from inline as we said) to _block_.

An example:

```css
header,
section,
footer,
aside,
nav,
article,
figure {
  display: block;
}
```

This is not the optimal solution nor the recommended one, it's meh.

- ### The recommended approach

We get JavaScript involved in the play by fundamentally creating the elements from scratch as such:

```javascript
document.createElement('nav');
document.createElement('header');
document.createElement('article');
// etc
```

By the way, this code must be appended in the _head_ element either by linking to an external script or by writing the code inline using _script_ tag.

The problem with this though is there's more than 100 semantic HTML element in the spec. And this code seems pretty lacking and is not reliable on real world projects.

The best way to deal with this is by using _html5shiv_ (there's actually a funny story behind the debate whether it should be called shiv or shim).

The script is in this [repo](https://github.com/aFarkas/html5shiv).

There are two ways to get the script (you can check them out in README of the repository), either by using _Bower_ or manually installing it.

I prefer the manual installation via this [link](https://github.com/aFarkas/html5shiv/archive/master.zip):

1. After extracting the ZIP file, copy either files _dist/html5shiv.js_ or _dist/html5shiv-printshiv.js_ to your project's directory.
2. Include the copied script in the _head_ element
3. Add this comment in the _head_ element after all the stylesheets:

```html
<!--[if lt IE 9]>
  <script src="bower_components/html5shiv/dist/html5shiv.js"></script>
<![endif]-->
```

Problem solved. You can now safely forget about the older browsers!

## Thank you for reading!

I hope you learned something new and enjoyed reading!

Follow my blog and my [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one.

---
 
Thumbnail picture by [Hans Eiskonen](https://unsplash.com/@eiskonen?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/black-sedan-D9TK2X0Nj-U?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
