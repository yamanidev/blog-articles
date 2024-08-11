---
title: "Your Best Friend Before Google in Python! 👩‍💻"
description: "I share in this article the first source you should refer to before Google when it comes to Python, it is the built in manual."
canonicalUrl: "https://mohamedyamani.com/blog/your-best-friend-before-google-in-python/"
pubDate: 2021-01-29
image: "/images/thumbnails/your-best-friend-before-google-in-python.jpg"
imageAlt: "women sitting on rock near body of water"
---

It is no secret (or so I hope) that when programming in any given language, consulting the official documentation (as most of them are up-to-date, extensively detailed and thorough) is crucial to understanding the intricacies and details of the technology we're fiddling with.

But sometimes, we find ourselves wasting a lot of time looking for something very specific due to the disorganization of the documentation. Luckily enough, we have a generous method at our proposal, which is the **help() method**

### Allow me to introduce you to your best friend

**help()** is a method (function) that invokes a built-in help system which displays official and brief documentation of:

- **Modules**
- **Classes** (user-defined or built-in)
- **Methods** (user-defined or built-in)
- **Keywords**

Oh and by the way, if you want to display all Python's keywords:

```python
from keyword import kwlist
print(kwlist)
```

The method takes in an object as parameter `help(object)`:

```python
help(str)

help(int)

help(help)
# I know some of you like myself would attempt this haha
# It is a valid statement
```

### So how do I use it?

There are two ways to use this method:

- **By passing an argument**: as we did in the previous example above.
- **Without arguments**: which starts an interactive help system on the interpreter's console:

![Screenshot from 2021-01-29 13-05-49.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611921962315/QWRomHZi7.png)

### Why should I care?

If you want a brief, concise and official description or documentation about a certain object without going through the lengthy one available online, or if you want to quickly glance over or discover the different methods that can be used on an object, or if you don't have an internet connection available at a given time, **help()** is your go to!

### The End!

I hope you enjoyed reading this! Let me know how you find this type of short articles!

Follow me on [Twitter](https://twitter.com/yamanidev) for more!

Thumbnail picture by [Roberto Nickson](https://unsplash.com/@rpnickson?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/women-sitting-on-rock-near-body-of-water-vRAYwESFc-U?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
