---
title: "Let's Understand CSS: Inheritance"
description: 'Most CSS bugs come from conflicting styles. Understanding how CSS deals with them can help you avoid them. In this article, I explain one of the fundamental concepts for resolving them: inheritance.'
canonicalUrl: 'https://mohamedyamani.com/blog/lets-understand-css-inheritance/'
pubDate: 2023-10-16
image: "/images/thumbnails/lets-understand-css-inheritance.jpg"
imageAlt: "a close up of a red and blue object"
---

Most CSS bugs come from conflicting styles which most people solve by slapping the notorious `!important` at them, or by resorting to inline styles instead.

The only fix to this is by understanding how CSS deals with conflicting rules, and how to use it to your advantage. This mostly includes 3 fundamental concepts:

- Cascade.
- Specificity.
- Inheritance.

In this article, I'll explain the last concept.

Another equally important concept is the Box Model which I wrote about [2 years ago](https://mohamedyamani.com/blog/understanding-the-box-model-in-css/), that should explain why I describe myself as _sometimes a blogger_.

I'll be writing more often on fundamental CSS concepts that must be understood for smooth sailing with CSS, otherwise you'll relate to the memes.

Whatever you do though, don't be this guy.

![developer meme: hates to write CSS but still won't learn it](/images/meme-dev-humor-hate-to-write-css-but-still-not-gonna-learn.jpg)

If you're someone who doesn't struggle with reading MDN docs, I recommend you skip this article to read the MDN one and wrap up inheritance in a few minutes: [Inheritance MDN link](https://developer.mozilla.org/en-US/docs/Web/CSS/Inheritance).

If you wish to stick around, buckle up.

---

One of the best ways to learn about tech stuff is by thinking about how to build them yourself. What would be the process like? What decisions and compromises will you make to achieve X?

Even if you're not able to answer these questions -understandably so-, they remain interesting questions to ask and find answers to.

Shifting your thinking to how to build a tool will give you a chance to understand why certain things behave the way they do, why they were built the way they were etc.

Keeping in mind the properties you know and putting all your CSS knowledge aside, what do you think styling would be like?

What's the architecture of styling web pages like?

The way I see it, it will be very explicit and verbose.

Since styling like this is not an option,

```html
<ul class="cool-list">
  <li>banana</li>
  <li>monkey</li>
  <li>idk</li>
</ul>
```

```css
.cool-list {
  color: red;
  font-weight: 700;
}
```

it has to be something like this:

```html
<ul>
  <li class="not-so-cool-li">banana</li>
  <li class="not-so-cool-li">monkey</li>
  <li class="not-so-cool-li">idk</li>
</ul>
```

```css
.not-so-cool-li {
  color: red;
  font-weight: 700;
}
```

It would be a nightmare to write and worse to maintain. Not so cool indeed.

This is why inheritance was implemented. To make styling web pages compact and clean.

Instead of having to style each HTML element separately, you can style a parent and the styles will get applied to its children **at all nested levels**.

```html
<body class="cool-body">
  <main>
    <header>
      <h1>Some cool title I bet</h1>
    </header>

    <p>Bla bla bla <span>special bla bla</span></p>
  </main>
</body>
```

```css
.cool-body {
  color: red;
  font-size: 20px;
  font-weight: 700;
}
```

Quick reminder:

- Regardless of the nesting level, if element A is in any shape contained inside of element B, then element A is a child of element B.
- The level of nesting is what determines if a child is a direct or an indirect one. If it's only nested one level deep, it's a direct child, otherwise it's an indirect one.
- `<h1>` is a direct child of `<header>` and an indirect child to `<main>`.
- `<span>` is a direct child of `<p>` and an indirect child to `<main>`.

All of the children of `<body>` will _inherit_ the style declarations of the class `cool-body`. i.e., everything will look tedious.

## How it works

So what happens when different parents have conflicting style declarations? The conflict is having different values for the same CSS property.

One of them must be picked of course.

The algorithm to pick the inherited styles is pretty straightforward: we pick the styles of the closest parent. And since the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Using_the_Document_Object_Model#what_is_a_dom_tree) is a tree data structure, it's easy to do that.

```html
<body>
  <main class="cool-main">
    <header class="cool-header">
      <h1>Some cool title I bet</h1>
    </header>

    <p>Bla bla bla <span>special bla bla</span></p>
  </main>
</body>
```

```css
.cool-main {
  color: black;
}

.cool-header {
  color: red;
}
```

- `<h1>` will take take `cool-header`'s style because it's the closest parent.
- `<p>` will take `cool-main`'s style because it's the closest parent.
- `<span>` will take `cool-main`'s style because it's the closest parent.

Thankfully, not all properties are inherited. Can you imagine passing down properties like `width`, `display`, `border` etc?

Most of the inherited properties are typography related, with some other ones you've never heard of. You can find the list of these properties in this [Stack Overflow answer](https://stackoverflow.com/a/5612360/14034906).

---

Hope you learned something!

Don't relate to CSS memes.

---
 
Thumbnail picture by [Jr Korpa](https://unsplash.com/@jrkorpa?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/a-close-up-of-a-red-and-blue-object-oOqNQCIlt94?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
