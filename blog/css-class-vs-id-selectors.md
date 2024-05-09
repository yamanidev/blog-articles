---
title: 'CSS Class vs ID Selectors — Understanding the Difference!'
description: 'In this article I break down two CSS selectors, classes and ids, how to use them to select HTML elements as well the difference between them.'
canonicalUrl: "https://mohamedyamani.com/blog/css-class-vs-id-selectors/"
pubDate: 2021-03-21
image: "/images/thumbnails/css-class-vs-id-selectors.jpg"
imageAlt: "two monitor desk setup with red backlights showing code on one screen and spotify on the other with a phone between them"
---

When I first started learning about CSS (and I still am) I felt fabulous applying styles to elements and making the web page look decent (Although still not making the 21st century in style). Till I met one day the ID and class selectors where were my first obstacle in my learning journey. I just couldn’t understand what was the difference between the two, if both of them allows me to select HTML elements so I could apply style rules to them, why do we need two!

Today I’ll try to explain that in a way that I wished someone would to my younger self, let’s get started!

## The magnificent CSS

All CSS does is **_apply style_** rules to certain HTML elements. With that being said, we can distinguish two steps:

1. Selecting HTML element(s)

2. Applying style rules to it/them

In this article we will be focusing on the first part.

## How to use class and id

One of the many ways we can select HTML elements is by using the attributes **class** and **id**:

```html
<h1 id="cool-heading">Big banana</h1>
<p class="cool-text">I shall be selected</p>
```

And the way we can reference them in CSS is by prefixing:

- The ID name with “#”

- The class name with “.”

```css
#cool-heading {
    // CSS styles
}
.cool-text {
   // CSS styles
}
```

## The fight: ID vs Class

### ID

- It is used to identify **unique elements** to change their presentation (with CSS) and/or their behavior (with JavaScript).

- An HTML element can only have one ID.

- An ID can only be assigned to one HTML element.

- IDs can be used to navigate to certain parts of the page:

**Example:**

Adding an anchor that takes you to the contacts section:

```html
<!-- HTML -->
<a href="#contacts">Show me da wey</a>
<!-- other HTML -->
<div id="contacts">
  <!-- Contacts section -->
</div>
```

- an ID has a higher specificity than a class.

The best definition I found of **specificity** is [W3S’s](https://www.w3schools.com/css/css_specificity.asp) (you can learn more about it there):

> If there are two or more conflicting CSS rules that point to the same element, the browser follows some rules to determine which one is most specific and therefore wins out.

> Think of specificity as a score/rank that determines which style declarations are ultimately applied to an element.

For example if you apply to the same element (selected once by ID and then by class) conflicting styles, the styles applied via ID will win:

```html
<p class="weak" id="stronk">What's my color?</p>
```

```css
#stronk {
  color: brown;
}
.weak {
  color: black;
}
```

Due to the cascading nature of CSS (last rule applied overrides) we expect that the styles for the class **weak** are the ones applied. But that is not the case!

The reason for that being the **specificity hierarchy** that favors IDs over classes!

Learning about it is crucial and it will save you a lot of time in the future understanding why certain styles are not applied.

### Class

- Is not a unique identifier.

- A class can identify multiple HTML elements.

- We can assign many classes to an HTML element:

```html
<!-- assigning class1 class2 and class3 to p -->
<p class="class1 class2 class3">I am popular</p>
```

- A class has an inferior **specificity** (as we saw in previous examples)

## What does JavaScript have to say?

One of the things I love the most about programming is that the questions you raise can be often answered by the environment on which you develop!

If you are familiar with JavaScript, you will notice that it points out some differences between IDs and Classes!

```javascript
// Notice that
// the method's name says Elements and not Element
// It returns therefore an HTMLCollection
// And not an individual HTML element
console.log(document.getElementsByClassName('some-class'));
// While this method says Element
console.log(document.getElementById('some-id'));
```

## Thank you for reading!

These were the differences between Classes and IDs, I hope you enjoyed reading the article!

Follow my blog and my [Twitter](https://twitter.com/yamanidev) for more.

Have a nice one!

---

Thumbnail picture by [Fotis Fotopoulos](https://unsplash.com/@ffstop?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/black-remote-control-on-red-table-6sAl6aQ4OWI?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
